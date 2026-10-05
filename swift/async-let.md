# `async let` runs child tasks in parallel

`async let` starts a child task right away and lets you keep going. You only
`await` the value when you actually need it, so two independent calls overlap
instead of running back to back. If the scope exits before you await, the child
task is cancelled and awaited implicitly.

```swift
async let screenshot = captureScreen()
async let transcript = transcribe(audio)
let (image, text) = try await (screenshot, transcript)
```
