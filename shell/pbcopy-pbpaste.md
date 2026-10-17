# Pipe to the clipboard with `pbcopy` and `pbpaste`

```sh
git diff | pbcopy
pbpaste | wc -l
```

`pbcopy` reads stdin into the system clipboard, `pbpaste` writes the clipboard to stdout.
Handy for grabbing command output without selecting it, or for running a quick
transform on whatever I just copied, e.g. `pbpaste | sort -u | pbcopy`.
