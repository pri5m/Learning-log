
'''
pri5m:~/workspace $ mysql-ctl start
Installing MySQL
 * Stopping MySQL database server mysqld
   ...done.
 * Starting MySQL database server mysqld
   ...done.
 * Checking for tables which need an upgrade, are corrupt or were 
not closed cleanly.

MySQL 5.5 database added.  Please make note of these credentials:

       Root User: pri5m
   Database Name: c9

 * Starting MySQL database server mysqld
   ...done.
pri5m:~/workspace $ mysql-ctl cli
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 55
Server version: 5.5.57-0ubuntu0.14.04.1 (Ubuntu)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> ^CCtrl-C -- exit!
Aborted
pri5m:~/workspace $ mysql-ctl cli
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 57
Server version: 5.5.57-0ubuntu0.14.04.1 (Ubuntu)

Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> help;

For information about MySQL products and services, visit:
   http://www.mysql.com/
For developer information, including the MySQL Reference Manual, visit:
   http://dev.mysql.com/
To buy MySQL Enterprise support, training, or other products, visit:
   https://shop.mysql.com/

List of all MySQL commands:
Note that all text commands must be first on line and end with ';'
?         (\?) Synonym for `help'.
clear     (\c) Clear the current input statement.
connect   (\r) Reconnect to the server. Optional arguments are db and host.
delimiter (\d) Set statement delimiter.
edit      (\e) Edit command with $EDITOR.
ego       (\G) Send command to mysql server, display result vertically.
exit      (\q) Exit mysql. Same as quit.
go        (\g) Send command to mysql server.
help      (\h) Display this help.
nopager   (\n) Disable pager, print to stdout.
notee     (\t) Don't write into outfile.
pager     (\P) Set PAGER [to_pager]. Print the query results via PAGER.
print     (\p) Print current command.
prompt    (\R) Change your mysql prompt.
quit      (\q) Quit mysql.
rehash    (\#) Rebuild completion hash.
source    (\.) Execute an SQL script file. Takes a file name as an argument.
status    (\s) Get status information from the server.
system    (\!) Execute a system shell command.
tee       (\T) Set outfile [to_outfile]. Append everything into given outfile.
use       (\u) Use another database. Takes database name as argument.
charset   (\C) Switch to another charset. Might be needed for processing binlog with multi-byte charsets.
warnings  (\W) Show warnings after every statement.
nowarning (\w) Don't show warnings after every statement.

For server side help, type 'help contents'

mysql> show databse;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'databse' at line 1
mysql> database;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'database' at line 1
mysql> show database;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'database' at line 1
mysql> clear
mysql> help;

For information about MySQL products and services, visit:
   http://www.mysql.com/
For developer information, including the MySQL Reference Manual, visit:
   http://dev.mysql.com/
To buy MySQL Enterprise support, training, or other products, visit:
   https://shop.mysql.com/

List of all MySQL commands:
Note that all text commands must be first on line and end with ';'
?         (\?) Synonym for `help'.
clear     (\c) Clear the current input statement.
connect   (\r) Reconnect to the server. Optional arguments are db and host.
delimiter (\d) Set statement delimiter.
edit      (\e) Edit command with $EDITOR.
ego       (\G) Send command to mysql server, display result vertically.
exit      (\q) Exit mysql. Same as quit.
go        (\g) Send command to mysql server.
help      (\h) Display this help.
nopager   (\n) Disable pager, print to stdout.
notee     (\t) Don't write into outfile.
pager     (\P) Set PAGER [to_pager]. Print the query results via PAGER.
print     (\p) Print current command.
prompt    (\R) Change your mysql prompt.
quit      (\q) Quit mysql.
rehash    (\#) Rebuild completion hash.
source    (\.) Execute an SQL script file. Takes a file name as an argument.
status    (\s) Get status information from the server.
system    (\!) Execute a system shell command.
tee       (\T) Set outfile [to_outfile]. Append everything into given outfile.
use       (\u) Use another database. Takes database name as argument.
charset   (\C) Switch to another charset. Might be needed for processing binlog with multi-byte charsets.
warnings  (\W) Show warnings after every statement.
nowarning (\w) Don't show warnings after every statement.

For server side help, type 'help contents'

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
5 rows in set (0.00 sec)

mysql> select @@hostname;
+----------------------------+
| @@hostname                 |
+----------------------------+
| pri5m-mysql-course-6280527 |
+----------------------------+
1 row in set (0.00 sec)

mysql> CREATE DATABASE hello_worl_db;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| hello_worl_db      |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
6 rows in set (0.00 sec)

mysql> create database hello_world_db;
Query OK, 1 row affected (0.00 sec)

mysql> DROP DATABASE hello_worl_db;
Query OK, 0 rows affected (0.01 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| hello_world_db     |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
6 rows in set (0.00 sec)

mysql> DROP DATABASE hello_world_db;
Query OK, 0 rows affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
5 rows in set (0.00 sec)

mysql> CREATE DATABASE dog_walking_app;
Query OK, 1 row affected (0.00 sec)

mysql> USE dog_walking_app;
Database changed
mysql> SELECT database();
+-----------------+
| database()      |
+-----------------+
| dog_walking_app |
+-----------------+
1 row in set (0.00 sec)

mysql> DROP DATABASE dog_waling_app;
ERROR 1008 (HY000): Can't drop database 'dog_waling_app'; database doesn't exist
mysql> DROP DATABASE dog_walking_app;
Query OK, 0 rows affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
5 rows in set (0.00 sec)

mysql> CREATE TABLE cats
    -> name VARCHAR(100),
    -> age INT
    -> );
ERROR 1046 (3D000): No database selected
mysql> CREATE DATABASE cat_app;
Query OK, 1 row affected (0.00 sec)

mysql> SELECT DATABASE cat_app;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'cat_app' at line 1
mysql> CREATE TABLE cats name VARCHAR(100), age INT );
ERROR 1046 (3D000): No database selected
mysql> USE cat_app;
Database changed
mysql> CREATE TABLE cats name VARCHAR(100), age INT );
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'name VARCHAR(100), age INT )' at line 1
mysql> CREATE TABLE cats (name VARCHAR(100), age INT);
Query OK, 0 rows affected (0.01 sec)

mysql> SHOW TABLES;
+-------------------+
| Tables_in_cat_app |
+-------------------+
| cats              |
+-------------------+
1 row in set (0.00 sec)

mysql> SHOW COLUMNS FROM cats
    -> ;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | YES  |     | NULL    |       |
| age   | int(11)      | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> DESC cats;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| name  | varchar(100) | YES  |     | NULL    |       |
| age   | int(11)      | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
2 rows in set (0.01 sec)

mysql> DROP TABLE cats;
Query OK, 0 rows affected (0.01 sec)

mysql> SHOW COLUMNS FROM cats
    -> ;
ERROR 1146 (42S02): Table 'cat_app.cats' doesn't exist
mysql> CREATE TABLE pastries (
    -> name VARCHAR(50),
    -> quantity int);
Query OK, 0 rows affected (0.01 sec)

mysql> SHOW TABLES;
+-------------------+
| Tables_in_cat_app |
+-------------------+
| pastries          |
+-------------------+
1 row in set (0.01 sec)

mysql> SHOW CLOUMNS FROM pastries;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'CLOUMNS FROM pastries' at line 1
mysql> SHOW COLUMNS FROM pastries;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| name     | varchar(50) | YES  |     | NULL    |       |
| quantity | int(11)     | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
2 rows in set (0.00 sec)

mysql> DROP TABLE pastries;
Query OK, 0 rows affected (0.00 sec)
'''
