# Keep an Ollama model loaded with `keep_alive`

Ollama unloads a model after 5 minutes idle by default, so the next request
pays the cold-load cost again. Sending a request with no prompt just loads the
model, and `keep_alive` controls how long it sticks around:

```sh
# load and keep it in memory indefinitely
curl http://localhost:11434/api/generate -d '{"model": "qwen2.5vl:3b", "keep_alive": -1}'
# unload it right now
curl http://localhost:11434/api/generate -d '{"model": "qwen2.5vl:3b", "keep_alive": 0}'
```

`ollama ps` shows what's loaded and when it'll be evicted. `OLLAMA_KEEP_ALIVE`
sets the default for the whole server.
