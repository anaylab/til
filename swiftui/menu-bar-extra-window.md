# `MenuBarExtra` can show a window, not just a menu

`MenuBarExtra` (macOS 13+) defaults to `.menu` style, which turns its content
into a plain dropdown menu, so sliders, text fields, and custom layouts don't
really work. Switching to `.window` style shows the content in a popover-style
panel under the status item instead, and it renders like any normal SwiftUI view.

```swift
MenuBarExtra("Wisp", systemImage: "sparkles") {
    SettingsPanel()
        .frame(width: 280)
}
.menuBarExtraStyle(.window)
```
