# Let `git bisect run` find the bad commit for you

```sh
git bisect start
git bisect bad              # current commit is broken
git bisect good v1.2.0      # this one was fine
git bisect run ./test.sh
git bisect reset
```

The script's exit code decides each step: 0 means good, 1–127 (except 125) means
bad, and 125 means "can't test this commit, skip it". Git binary-searches the
range on its own. `git bisect reset` puts you back on the branch you started from.
