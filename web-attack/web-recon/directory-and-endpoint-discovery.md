# Directory & endpoint discovery

### feroxbuster

feroxbuster is a fast tool for brute-forcing | directories | files |hidden endpoint.

```actionscript-3
#install in kali-linux 
sudo apt update && sudo apt install -y feroxbuster

# Basic usage of feroxbuster
feroxbuster -u https://example.com
```



\
Enumeration flags

```applescript
# custom wordlist SecLists (best choice)
-w /path/to/wordlist.txt

# multiple subdomains
cat subs.txt | feroxbuster --stdin -w /path/to/wordlist.txt

# Show only useful responses
-s 200,301,302,403

#Adding extensions
-x php,html,js,json,txt

# Increase speed (threads)
-t 50

# Recursive scanning (go deeper automatically)
-r

#Save output
-o scan.txt

```

### Real-world example with good setup

```applescript
# one of the good setup 

feroxbuster -u https://example.com \
-w /usr/share/seclists/Discovery/Web-Content/common.txt \
-x php,html,js,json \
-t 40 \
-r \
-o output.txt
```
