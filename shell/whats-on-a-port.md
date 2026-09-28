# Find what's listening on a port

```sh
lsof -nP -iTCP:11434 -sTCP:LISTEN
```

`-n` and `-P` skip DNS and port-name lookups, so it returns instantly. The PID is
in the second column; `kill <pid>` if it's a stale server.
