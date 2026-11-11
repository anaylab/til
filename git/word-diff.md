# `git diff --word-diff` for prose and one-line changes

A normal diff marks a whole line as changed even if only one word moved, which is annoying for READMEs and long strings. `--word-diff` shows the change inline instead.

```sh
git diff --word-diff
# the quick [-brown-]{+red+} fox

git diff --word-diff=color   # same thing, colors instead of [- -] / {+ +}
```

Works with `git show` and `git log -p` too.
