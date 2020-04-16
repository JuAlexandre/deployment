# Create a new user in MySQL for a specific database

Replace [new_user], [new_password] and [my_db]:

```sql
CREATE USER '[new_user]'@'localhost' IDENTIFIED BY '[new_password]';
GRANT ALL ON [my_db].* TO '[new_user]'@'localhost';
FLUSH PRIVILEGES;
```
