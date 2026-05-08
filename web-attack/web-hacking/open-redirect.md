# Open Redirect

```
# find subdomains 
subfinder -d xyz.com -o sub.txt

# gather urls on this sub domain
cat sub.txt | waybackurls > end.txt

# find the openredirect urls only
cat end.txt | grep "=http" | qsreplace  "https://evil.com" | httpx-toolkit -fr -location
```

{% embed url="https://github.com/1ndianl33t/Gf-Patterns/blob/master/redirect.json" %}

```
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
