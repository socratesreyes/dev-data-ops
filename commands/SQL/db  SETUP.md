logging in 
Connect with:

bash

```bash
docker compose exec mysql mysql -uroot -plab support
docker compose exec postgres psql -U postgres support
```

![[Pasted image 20261016191519.png|467]]


![[Pasted image 20261016191625.png|487]]

![[Pasted image 20261016191653.png|480]]


non docker direct host 

![[Pasted image 20261016191749.png|535]]


mysql -uroot -plab support
psql -U postgres support


or temporary user switch
sudo -i -u **postgres** psql support




----------------------------

SHOW TABLES;

DESCRIBE tables


![[Pasted image 20261016232018.png]]