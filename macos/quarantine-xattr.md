# Clearing the quarantine flag with `xattr`

Anything downloaded through a browser gets a `com.apple.quarantine` extended
attribute, and that's what makes Gatekeeper pop the "downloaded from the
internet" prompt (or flat-out refuse an unsigned build). You can see it and
strip it from the terminal:

```sh
xattr -l ~/Downloads/SomeTool.app                          # list attributes
xattr -dr com.apple.quarantine ~/Downloads/SomeTool.app    # remove it, recursively
```

Only do this for stuff you actually trust, since it skips that first-launch check.
