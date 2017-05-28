# Access-MySql-

mysql -u root -p

# Backup

mysqldump -u [username] -p[password] [dbname] > [dbname].sql

# Buscar Repetidos

SELECT codigo, COUNT(*) estoyRepetido FROM codigos GROUP BY codigo HAVING estoyRepetido > 1;
