# Spotlight search from the terminal

```sh
mdfind -name "Package.swift"
mdfind -onlyin ~/Downloads "kMDItemContentType == 'com.adobe.pdf'"
```

Much faster than `find` for whole-disk searches because it hits the Spotlight
index. It won't see folders excluded from Spotlight.
