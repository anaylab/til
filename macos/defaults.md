# Reading app preferences with `defaults`

```sh
defaults domains | tr ',' '\n' | grep -i myapp   # find the domain
defaults read com.example.MyApp                  # dump everything
defaults write com.example.MyApp SomeKey -bool NO
```

Quit the app before `write`, otherwise it can overwrite your change with its
in-memory copy when it exits.
