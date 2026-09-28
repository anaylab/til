# Global event monitors can't swallow events

`NSEvent.addGlobalMonitorForEvents(matching:handler:)` only *observes* events
sent to other apps; it can't modify or block them. Key events also require the
app to be trusted for Accessibility. To consume events system-wide you need a
`CGEvent` tap instead.
