# `withCheckedContinuation` bridges callbacks into async/await

Wrapping an old completion-handler API is just a continuation. You must resume
it exactly once on every path. The "checked" version logs a runtime warning if
you forget to resume (the caller hangs forever) or resume twice, which is why
I reach for it before the `Unsafe` variant.

```swift
func requestAccess() async -> Bool {
    await withCheckedContinuation { continuation in
        legacyRequestAccess { granted in
            continuation.resume(returning: granted)
        }
    }
}
```

If the callback can fail, use `withCheckedThrowingContinuation` and call `resume(throwing:)`.
