---
description: >-
  httpx is a fast and multi-purpose HTTP toolkit that allows running multiple
  probes using the retryable http library
---

# httpx Tool

live subdomains

```
# httpx Save only live subdomains
httpx -l subs.txt -silent -o live.txt

#Status codes (200, 403, etc.)|Page titles|Technologies used|IP addresses
httpx -l subs.txt -status-code -title -tech-detect -ip

```

```
# To filter your sub.txt and find only live domains:

cat sub.txt | httpx -mc 200,301,302,403 -o live_subs.txt
```
