# Access-MySql-

mysql -u root -p

# Backup

mysqldump -u USUARIO -p DBNAME > NAMEBACKUP.sql

```-- // Te pedira la clave```

# Buscar Repetidos

SELECT codigo, COUNT(*) estoyRepetido FROM codigos GROUP BY codigo HAVING estoyRepetido > 1;
