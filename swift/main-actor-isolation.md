# `@MainActor` on a class isolates every member

Marking a class `@MainActor` makes all its properties and methods main-actor
isolated, so calling them from a background task needs `await`. Use
`nonisolated` on members that don't touch UI state to opt them out.

```swift
@MainActor
final class Overlay {
    var isVisible = false
    nonisolated func log(_ s: String) { print(s) }
}
```
