# Unstage a file with `git restore --staged`

I used to reach for `git reset HEAD <file>` to unstage something, which always felt like the wrong verb. `git restore --staged` does the same thing and says what it means. It only touches the index, so your edits in the working tree stay put.

```sh
git restore --staged notes.txt   # unstage, keep the changes
git restore notes.txt            # discard working-tree changes (careful, no undo)
```

Pass both `--staged --worktree` (or `-S -W`) to do both at once.
