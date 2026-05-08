# Open Redirect

```
# find subdomains 
subfinder -d xyz.com -o sub.txt

# gather urls on this sub domain
cat sub.txt | waybackurls > end.txt

# find the openredirect urls only
cat end.txt | grep "=http" | qsreplace  "https://evil.com" | httpx-toolkit -fr -location
```
