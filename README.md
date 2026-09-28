# TIL

Short notes on things I learn day to day, mostly Swift, macOS, and dev tooling.

## Swift
- [`@MainActor` on a class isolates every member](swift/main-actor-isolation.md)
- [`defer` blocks run in reverse order](swift/defer-order.md)
- [`some` vs `any`](swift/some-vs-any.md)
- [`@Observable` only tracks what you read](swift/observable-tracking.md)
- [`Task { }` keeps `self` alive until it finishes](swift/task-capture.md)

## macOS
- [Menu bar–only apps with `LSUIElement`](macos/lsuielement.md)
- [Reading app preferences with `defaults`](macos/defaults.md)
- [Silent screenshots from the terminal](macos/screencapture.md)
- [Spotlight search from the terminal](macos/mdfind.md)
- [Global event monitors can't swallow events](macos/global-monitor.md)

## Git
- [Crediting co-authors in a commit](git/co-authored-by.md)
- [`git switch -` jumps back to the last branch](git/switch-dash.md)
- [Find when a string was added with `git log -S`](git/pickaxe.md)
- [Fixup commits and `--autosquash`](git/autosquash.md)
- [Work on two branches at once with `git worktree`](git/worktree.md)

## Shell
- [Find what's listening on a port](shell/whats-on-a-port.md)
- [Print only the HTTP status with curl](shell/curl-status.md)
