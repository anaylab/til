# Fixup commits and `--autosquash`

```sh
git commit --fixup=<sha>
git rebase -i --autosquash main
```

The fixup commit is automatically moved under `<sha>` and marked `fixup`, so the
rebase todo list is already in the right order. Set
`git config --global rebase.autoSquash true` to make it the default.
