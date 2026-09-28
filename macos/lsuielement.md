# Menu bar–only apps with `LSUIElement`

Setting `LSUIElement` to `YES` in `Info.plist` hides the Dock icon and the app
menu, so the app lives only in the status bar. Call
`NSApp.activate(ignoringOtherApps: true)` before showing a window, or it opens
behind whatever app is in front.
