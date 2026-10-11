# Keep the Mac awake with `caffeinate`

`caffeinate` holds a power assertion so the Mac doesn't sleep. The nice part is
you can hand it a command, and it only keeps the machine awake until that
command exits, so long model pulls don't die halfway when the lid timer kicks in.

```sh
caffeinate -i ollama pull qwen2.5vl:3b   # no idle sleep until the pull finishes
caffeinate -d -t 3600                    # keep the display on for an hour
```

`-i` blocks idle sleep, `-d` blocks display sleep, and `-w <pid>` waits on a
process that's already running.
