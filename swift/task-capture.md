# `Task { }` keeps `self` alive until it finishes

A `Task` closure captures `self` strongly, but the reference is dropped once the
task completes, so short tasks don't leak. It matters for long-lived work, such
as an infinite `for await` loop, which keeps the object alive forever. For those,
use `[weak self]` or store the task and `cancel()` it in `deinit`/on teardown.
