# Access-MySql-

mysql -u root -p

# Backup

mysqldump -u USUARIO -p DBNAME > NAMEBACKUP.sql

```-- // Te pedira la clave```

# Solucionar problema de durecion a la hora de exportar bases de datos enormes.

https://ottomatik.groovehq.com/knowledge_base/topics/solving-error-2013-lost-connection-to-mysql-server-during-query-when-dumping-table

# Buscar Repetidos

SELECT codigo, COUNT(*) estoyRepetido FROM codigos GROUP BY codigo HAVING estoyRepetido > 1;
