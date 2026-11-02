# `git stash` skips untracked files unless you pass `-u`

Plain `git stash` only saves changes to files git already tracks. Brand-new files stay sitting in the working tree, which is confusing when you stash to get a clean checkout and they're still there.

```sh
git stash -u   # --include-untracked: also stash new files
git stash -a   # --all: untracked *and* ignored files
```

`-a` will sweep up things like build folders too, so `-u` is usually the one I want.
