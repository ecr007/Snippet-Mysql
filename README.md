# Access-MySql-

mysql -u root -p

# Backup

mysqldump -u USUARIO -p DBNAME > NAMEBACKUP.sql

```-- // Te pedira la clave```

# Cambiar contraseña

Si es la primera vez:
```SET PASSWORD = PASSWORD('your_new_password');```

Si es la segunda vez, opcion a:
```UPDATE mysql.user SET Password=PASSWORD('your_new_password') WHERE User='root';```

Si es la segunda vez, opcion b: 
```ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPass';```

Fuente: https://stackoverflow.com/questions/33467337/reset-mysql-root-password-using-alter-user-statement-after-install-on-mac

# Solucionar problema de durecion a la hora de exportar bases de datos enormes.

https://ottomatik.groovehq.com/knowledge_base/topics/solving-error-2013-lost-connection-to-mysql-server-during-query-when-dumping-table

# Buscar Repetidos

SELECT codigo, COUNT(*) estoyRepetido FROM codigos GROUP BY codigo HAVING estoyRepetido > 1;

# Importar Datos a una tabla

```
mysql> use your_db_name;

mysql> source /opt/file.sql;
```

# PATH For MySQL
```
ln -s /usr/local/mysql/bin/mysql /usr/local/bin/mysql
```

# Ver Variables Globales en MySQL

```
SHOW VARIABLES;

O

SHOW VARIABLES LIKE '%max%';

```

# Ver listado de procesos en MySql

```show processlist;```

# Ver conexiones simultaneas sin cerrar:

```show status where `variable_name` = 'Threads_connected';```

# Para aumentar las conexiones maximas en MySql

```max_connections```

<p>On a shared hosting, "unlimited" means other users are unrestricted with their
resource using. Means they can eat up whole pool, while your consumption
remains modest</p>

<p>This is a limit of database's configuration. If you have permission to edit 
the configuration file of your database service, you can change max_connections
value.</p>

You can try running this SQL query (take care about this value!)
```SET GLOBAL max_connections = 512;```

and this to get current value of all variables:

```SHOW VARIABLES;```

or (for specific variable):

```SHOW GLOBAL VARIABLES LIKE '%max_connections%'```

## Numero maximo de conexiones que se han utilizado desde que se inicio el servicio

```SHOW STATUS WHERE `variable_name` = 'Max_used_connections';```

## Reset Mysql [Pierde configuraciones globales]

```sudo /etc/init.d/mysql restart```

# Reset Normal ##

```sudo service mysql restart```
