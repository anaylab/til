# Text-to-speech from the terminal with `say`

macOS ships a TTS command, `say`, which makes a decent zero-setup fallback
while a real TTS server is still warming up. It can also write straight to an
audio file instead of playing anything, handy for quick test clips:

```sh
say "build finished"                          # speak with the default voice
say -v Samantha -r 200 "a bit faster"         # pick a voice, words per minute
say -o hello.aiff "hello from the terminal"   # render to a file, silently
```

`say -v '?'` lists every installed voice along with its locale.
