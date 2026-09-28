# Silent screenshots from the terminal

```sh
screencapture -x out.png                 # whole screen, no shutter sound
screencapture -x -R 0,0,800,600 out.png  # just a rectangle
screencapture -c                         # to the clipboard
```

The first run from a new terminal app triggers the Screen Recording permission
prompt.
