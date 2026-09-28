# Find when a string was added with `git log -S`

```sh
git log -S "apiTimeout" --oneline
```

Lists commits where the number of occurrences of that string changed, i.e. where
it was added or removed. `-G` takes a regex instead. Add `-p` to see the diffs.
