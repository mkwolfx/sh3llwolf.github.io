# smart recon

```
# subfinder:
subfinder -d  https://turo.com  -o sub.txt 

# find active sub-domains:
cat sub.txt | httpx-toolkit -mc 200,301,302 -o active_subs.txt

# to get only 200 ok
cat active_subs.txt | httpx -mc 200 -silent > definitive_targets.txt

# Find the parameters on that
arjun -i active_subs.txt -oT output.txt

# Then run Arjun on the filtered list
arjun -i definitive_targets.txt -oT output.txt --stable
```
