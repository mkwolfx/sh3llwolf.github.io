# smart recon

```
# subfinder:
subfinder -d  https://turo.com  -o sub.txt 

# find active sub-domains:
cat sub.txt | httpx-toolkit -mc 200,301,302 -o active_subs.txt

# Find the parameters on that
arjun -i active_subs.txt -oT output.txt
```
