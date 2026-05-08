# Open Redirect

```applescript
# find subdomains 
subfinder -d xyz.com -o sub.txt

# find active subdomains
cat sub.txt | httpx-toolkit -mc 200,301,302 -o live_subs.txt

# gather urls on this sub domain
cat live_subs.txt | waybackurls > end.txt

# find the openredirect urls only
cat end.txt | grep "=http" | qsreplace  "https://evil.com" | httpx-toolkit -fr -location

# to save the file 
cat end.txt | grep "=http" | qsreplace "https://evil.com" > fuzzed_urls.txt

# Run this to see which URLs are "live" redirects:
cat fuzzed_urls.txt | httpx-toolkit -status-code -location -title -mc 301,302,307,308
```

{% embed url="https://github.com/1ndianl33t/Gf-Patterns/blob/master/redirect.json" %}

```applescript
// openredirect paths above link and down few.

"Lmage_url=",
"Open=",
"callback=",
"cgi-bin/redirect.cgi",
"cgi-bin/redirect.cgi?",
"checkout=",
"checkout_url=",
"continue=",
"data=",
"dest=",
"destination=",
"dir=",
"domain=",
```
