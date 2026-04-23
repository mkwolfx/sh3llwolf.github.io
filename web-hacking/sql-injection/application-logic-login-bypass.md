# application logic (login bypass)

```applescript
#SELECT * FROM users WHERE username = 'wiener' AND password = 'bluecheese'
```

an attacker can log in as any user without the need for a password. They can do this using the SQL comment <mark style="color:$success;">sequence</mark> <mark style="color:$success;"></mark><mark style="color:$success;">`--`</mark> to remove the password check from the `WHERE` clause of the query.

```cobol
#SELECT * FROM users WHERE username = 'administrator'--' AND password = ''
```

This query returns the user whose `username` is `administrator` and successfully logs the attacker in as that user.

```
# the value: administrator'--
```

