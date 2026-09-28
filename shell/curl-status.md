# Print only the HTTP status with curl

```sh
curl -s -o /dev/null -w "%{http_code}\n" http://localhost:8004/health
```

`-w` also knows `%{time_total}`, `%{size_download}` and friends, which makes it a
quick latency check.
