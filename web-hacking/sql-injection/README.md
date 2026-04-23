# SQL-Injection

SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. This can allow an attacker to view data that they are not normally able to retrieve. This might include data that belongs to other users, or any other data that the application can access. In many cases, an attacker can modify or delete this data

### <mark style="color:blue;">How to detect SQL injection vulnerabilities</mark>

* The single quote character `'` and look for errors or other anomalies.
* Boolean conditions such as `OR 1=1` and `OR 1=2`, and look for differences in the application's responses.

| Technique                | Base Syntax (`' OR <true> --`)                      | Altered Syntax (`' OR <false> --`)                  | Expected Difference if Vulnerable                                                                                                    |
| ------------------------ | --------------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Boolean-Based            | `' OR 1=1 --`                                       | `' OR 1=2 --`                                       | True: full dataset; False: empty/error [zindagitech](https://zindagitech.com/what-is-sql-injection-attack-and-how-can-we-detect-it/) |
| Time-Based               | `' OR IF(1=1, SLEEP(5), 0) --`                      | `' OR IF(1=2, SLEEP(5), 0) --`                      | True: 5s delay; False: instant [zindagitech](https://zindagitech.com/what-is-sql-injection-attack-and-how-can-we-detect-it/)         |
| Original Value Reference | `CASE WHEN (1=1) THEN original_col ELSE 'diff' END` | `CASE WHEN (1=2) THEN original_col ELSE 'diff' END` | True uses base; False substitutes stackoverflow+1                                                                                    |
