## Increase MySQL max_connections on EY Cloud

The default limit is 300.

To increase the limit on the fly, run this from the MySQL CLI:

```
set global max_connections = 600;
```

To increase the limit permanently, create the file `/etc/mysql.d/max_connections.cnf`:

```
[mysqld]
max_connections			= 600
```

then restart MySQL.

_You can also use this method to change other settings for mysqld (MySQL server) or mysqldump. Check the [MySQL Documentation](https://dev.mysql.com/doc/refman/5.7/en/mysqld-option-tables.html) for a complete list of configurable options._
