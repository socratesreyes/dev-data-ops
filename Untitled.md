```mysql
SELECT priority, status, category, opened_at FROM cases;
+----------+--------+-------------+---------------------+

| priority | status | category    | opened_at           |
+----------+--------+-------------+---------------------+

| high     | closed | transport   | 2026-10-01 09:00:00 |
| medium   | open   | portal      | 2026-10-05 10:00:00 |
| high     | closed | network     | 2026-10-06 08:30:00 |
| low      | open   | enhancement | 2026-10-07 13:00:00 |
| high     | open   | transport   | 2026-10-09 07:00:00 |
| medium   | closed | portal      | 2026-10-10 09:00:00 |
| high     | open   | transport   | 2026-10-12 11:00:00 |
| medium   | open   | network     | 2026-10-14 15:00:00 |
+----------+--------+-------------+---------------------+
8 rows in set (0.00 sec)
```

![](attachments/Pasted%20image%2020261018002944.png)

```mysql
SELECT * FROM cases LIMIT 2;
+---------+-----------+---------------------+---------------------+----------+-----------+--------+------------------------+

| case_id | client_id | opened_at           | closed_at           | priority | category  | status | subject                |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+------------------------+

|       1 |         1 | 2026-10-01 09:00:00 | 2026-10-01 15:00:00 | high     | transport | closed | SFTP login failing     |
|       2 |         1 | 2026-10-05 10:00:00 | NULL                | medium   | portal    | open   | Portal slow on reports |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+
2 rows in set (0.00 sec)
```

![](attachments/Pasted%20image%2020261018012613.png)
![](attachments/Pasted%20image%2020261018231847.png)

---

# ORDER BY

![](attachments/Pasted%20image%2020261018085716.png)
![](attachments/Pasted%20image%2020261018090056.png)
![](attachments/Pasted%20image%2020261018113439.png)

Everything is sorted by ascending by default.
`ORDER BY '' DESC;`
![](attachments/Pasted%20image%2020261018140047.png)

Tip: Default is ascending, so no need to type `ASC`.

![](attachments/Pasted%20image%2020261018142159.png)

# where 10

# SELECT COUNT

![](attachments/Pasted%20image%2020261018224909.png)

---
# WHERE
* `WHERE != 24` (not equal)  
* `WHERE <= 24` (less than or equal)  
* `WHERE id BETWEEN 25 AND 30` (self-explanatory)  

For text:
```mysql
SELECT protocol FROM transfers WHERE protocol = 'SFTP';  
```

![](attachments/Pasted%20image%2020261018233129.png)

# ADVANCED FILTERING IN AND OR

![](attachments/Pasted%20image%2020261019001346.png)

```mysql
SELECT * FROM cases WHERE priority = 'high' AND category = 'transport';
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+

| case_id | client_id | opened_at           | closed_at           | priority | category  | status | subject              |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+

|       1 |         1 | 2026-10-01 09:00:00 | 2026-10-01 15:00:00 | high     | transport | closed | SFTP login failing   |
|       5 |         4 | 2026-10-09 07:00:00 | NULL                | high     | transport | open   | AS2 receipts missing |
|       7 |         2 | 2026-10-12 11:00:00 | NULL                | high     | transport | open   | Files stuck in queue |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+
```

![](attachments/Pasted%20image%2020261019002421.png)

# MySQL Database Tutorial - 12 - Are you IN or are you NOT IN?

![](attachments/Pasted%20image%2020261019003646.png)
![](attachments/Pasted%20image%2020261019003740.png)

# 16 - Creating Custom Columns


select all * 
```
mysql> SELECT * FROM cases;
+---------+-----------+---------------------+---------------------+----------+-------------+--------+---------------------------+
| case_id | client_id | opened_at           | closed_at           | priority | category    | status | subject                   |
+---------+-----------+---------------------+---------------------+----------+-------------+--------+---------------------------+
|       1 |         1 | 2026-10-01 09:00:00 | 2026-10-01 15:00:00 | high     | transport   | closed | SFTP login failing        |
|       2 |         1 | 2026-10-05 10:00:00 | NULL                | medium   | portal      | open   | Portal slow on reports    |
|       3 |         2 | 2026-10-06 08:30:00 | 2026-10-08 12:00:00 | high     | network     | closed | VPN tunnel drops          |
|       4 |         3 | 2026-10-07 13:00:00 | NULL                | low      | enhancement | open   | Request: CSV export       |
|       5 |         4 | 2026-10-09 07:00:00 | NULL                | high     | transport   | open   | AS2 receipts missing      |
|       6 |         4 | 2026-10-10 09:00:00 | 2026-10-11 09:00:00 | medium   | portal      | closed | Password reset loop       |
|       7 |         2 | 2026-10-12 11:00:00 | NULL                | high     | transport   | open   | Files stuck in queue      |
|       8 |         5 | 2026-10-14 15:00:00 | NULL                | medium   | network     | open   | Cannot reach SFTP port 22 |
+---------+-----------+---------------------+---------------------+----------+-------------+--------+---------------------------+
8 rows in set (0.01 sec)

mysql> SHOW TABLES;
+-------------------+
| Tables_in_support |
+-------------------+
| cases             |
| clients           |
| transfers         |
| users             |
+-------------------+
4 rows in set (0.00 sec)
```





![](file-20261019213104517.png)