# Undo a bad `git reset --hard` with `git reflog`

Reset too far and the commits look gone, but they usually aren't. `git reflog` logs every place `HEAD` has pointed, so the old tip is still listed for a while (90 days by default for reachable entries) before garbage collection can touch it.

```sh
git reflog                 # find the entry from before the reset, e.g. HEAD@{2}
git reset --hard HEAD@{2}  # jump back to it
```

Caveat: this only saves committed work. Uncommitted changes wiped by `--hard` are really gone.
