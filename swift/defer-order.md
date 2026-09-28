# `defer` blocks run in reverse order

Multiple `defer` blocks in the same scope run last-in, first-out, like a stack.

```swift
func work() {
    defer { print("1") }
    defer { print("2") }
    print("body")
}
// body, 2, 1
```

Useful when cleanup has to undo setup in the opposite order.
