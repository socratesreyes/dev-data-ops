mysql> SELECT priority, status, category, opened_at FROM cases;
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


![[Pasted image 20261018002944.png]]


mysql> SELECT * FROM cases LIMIT 2;

+---------+-----------+---------------------+---------------------+----------+-----------+--------+------------------------+
| case_id | client_id | opened_at           | closed_at           | priority | category  | status | subject                |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+------------------------+
|       1 |         1 | 2026-10-01 09:00:00 | 2026-10-01 15:00:00 | high     | transport | closed | SFTP login failing     |
|       2 |         1 | 2026-10-05 10:00:00 | NULL                | medium   | portal    | open   | Portal slow on reports |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+------------------------+
2 rows in set (0.00 sec)

![[Pasted image 20261018012613.png]]


![[Pasted image 20261018231847.png]]

-----------------------------


ORDER BY

![[Pasted image 20261018085716.png]]


![[Pasted image 20261018090056.png]]



![[Pasted image 20261018113439.png]]


9 EVERYTHING IS SORT BY ASCENDING BY DEFAULT

ORDER BY '' DESC;![[Pasted image 20261018140047.png]]

tip is DEFAULT IS ASCENDING SO NO NEED TO TYPE ASC

![[Pasted image 20261018142159.png]]


where 10



SELECT COUNT

![[Pasted image 20261018224909.png]]

---------------------------
WHERE
WHERE != 24 (not equal)
WHERE <= 24 (less than or equal)
WHERE id BETWEEN 25 AND 30 ( SELF EXPLANATORY)

FOR TEXT
SELECT protocol FROM transfers WHERE protocol = 'SFTP';  
![[Pasted image 20261018233129.png]]



ADVANCE FILTERING IN AND OR


![[Pasted image 20261019001346.png]]

mysql> SELECT * FROM cases WHERE priority = 'high' AND  category = 'transport';
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+
| case_id | client_id | opened_at           | closed_at           | priority | category  | status | subject              |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+
|       1 |         1 | 2026-10-01 09:00:00 | 2026-10-01 15:00:00 | high     | transport | closed | SFTP login failing   |
|       5 |         4 | 2026-10-09 07:00:00 | NULL                | high     | transport | open   | AS2 receipts missing |
|       7 |         2 | 2026-10-12 11:00:00 | NULL                | high     | transport | open   | Files stuck in queue |
+---------+-----------+---------------------+---------------------+----------+-----------+--------+----------------------+



![[Pasted image 20261019002421.png]]



# MySQL Database Tutorial - 12 - Are you IN or are you NOT IN?

![[Pasted image 20261019003646.png]]
![[Pasted image 20261019003740.png]]


