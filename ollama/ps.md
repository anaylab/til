# See what Ollama has loaded with `ollama ps`

`ollama ps` lists the models currently sitting in memory, how big they are, and how long until they get unloaded. The `PROCESSOR` column is the useful bit: it tells you if the model is running fully on the GPU or got split between GPU and CPU, which is usually why things feel slow.

```sh
ollama ps
ollama stop qwen2.5vl:3b   # unload it right now
```

Handy after changing `keep_alive`, to check the model is really staying loaded (or really gone).
