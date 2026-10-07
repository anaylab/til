# `Task.sleep` throws when the task is cancelled

`Task.sleep` doesn't just quietly wake up early on cancellation, it throws
`CancellationError` right away. That makes it a handy debounce: cancel the old
task when new input arrives and the sleep bails out before the work runs. The
flip side is that `try? await Task.sleep(...)` swallows the error and carries on,
so check `Task.isCancelled` afterwards if you go that route.

```swift
searchTask?.cancel()
searchTask = Task {
    try await Task.sleep(for: .milliseconds(300)) // throws if cancelled
    await runSearch(query)
}
```
