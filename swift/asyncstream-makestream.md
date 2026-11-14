# `AsyncStream.makeStream` hands you the continuation directly

The old way to bridge a callback API into an `AsyncStream` was to grab the
continuation inside the build closure and stash it in an outer variable, which
always felt a bit hacky. Since Swift 5.9 there's `AsyncStream.makeStream(of:)`,
which just returns a `(stream, continuation)` tuple. Hand the stream to whoever
is iterating and keep the continuation wherever the callbacks fire.

```swift
let (levels, continuation) = AsyncStream.makeStream(of: Float.self)
meter.onLevel = { continuation.yield($0) }
meter.onStop = { continuation.finish() }
for await level in levels { updateWaveform(level) }
```
