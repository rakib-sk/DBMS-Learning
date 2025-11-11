<h1> Class2</h1>
<br />
step by step<br />

<h2>   আমাদের কাজ </h2>
১. Database তৈরি করা<br />
--Cmd<br />
--- SHOW databases; --> যে Database গুলো আছে আগে থেকে সেগুলো show করা<br />
-- Database তৈরি করার জন্য Cmd<br />
--- CREATE database DatabaseName; -->  নতুন Database  তৈরি করে।<br />

2. Database এ প্রবেশ করতে হবে <br />
--cmd
--->USE databaseName; --> ডাটাবেজ এ ঢোকায় <br/>

3. কাজ টেবিল তৈরি করা।<br />
-- CREATR TABLE product(
    Name VARCHAR(100),
    Discription VARCHAR(100),
    Price INT,
    Varaint VARCHAR(100)
   );
<br />
-- SHOW tables; --> এটার সাহায্যে Tables show  করানো হয়।
<br />
Explain:



<br />
<h2> Total terminal views </h2>
mysql -u root
mysql: Deprecated program name. It will be removed in a future release, use '/data/data/com.termux/files/usr/bin/mariadb' instead
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 3
Server version: 12.0.2-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> SHOW databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
| testdb             |
+--------------------+
6 rows in set (0.099 sec)

MariaDB [(none)]> CREATE database E-comarce
    -> ld
    -> ls
    -> clear
    -> /c
    -> \c;
ERROR: No query specified

MariaDB [(none)]> clear
MariaDB [(none)]> SHOW database
    -> \c;
ERROR: No query specified

MariaDB [(none)]> SHOW databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
| testdb             |
+--------------------+
6 rows in set (0.082 sec)

MariaDB [(none)]> \c;
ERROR: No query specified

MariaDB [(none)]> CREATE database ecomarce;
Query OK, 1 row affected (0.008 sec)

MariaDB [(none)]> SHOW databases;
+--------------------+
| Database           |
+--------------------+
| ecomarce           |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
| testdb             |
+--------------------+
7 rows in set (0.003 sec)

MariaDB [(none)]> SELECT database ecomarce;
ERROR 1054 (42S22): Unknown column 'database' in 'SELECT'
MariaDB [(none)]> SELECT database ecomarce;
ERROR 1054 (42S22): Unknown column 'database' in 'SELECT'
MariaDB [(none)]> SELECT DATABASE ecomarce;
ERROR 1054 (42S22): Unknown column 'DATABASE' in 'SELECT'
MariaDB [(none)]> SELECT ecomarce;
ERROR 1054 (42S22): Unknown column 'ecomarce' in 'SELECT'
MariaDB [(none)]> USE ecomarce;
Database changed
MariaDB [ecomarce]> SHOW table;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '' at line 1
MariaDB [ecomarce]> CREATE TABLE product{
    -> Name VARCHAR(100),
    -> Discription VARCHAR(100),
    -> Price INT,
    -> Variant VARCHAR(100)};
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '{
Name VARCHAR(100),
Discription VARCHAR(100),
Price INT,
Variant VARCHAR(100)}' at line 1
MariaDB [ecomarce]> CREATE TABLE product{ Name VARCHAR(100), Discription VARCHAR(100), Price INT, Variant VARCHAR(100)};
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '{ Name VARCHAR(100), Discription VARCHAR(100), Price INT, Variant VARCHAR(100)}' at line 1
MariaDB [ecomarce]> CREATE TABLE product( Name VARCHAR(100), Discription VARCHAR(100), Price INT, Variant VARCHAR(100));
Query OK, 0 rows affected (0.094 sec)

MariaDB [ecomarce]> SHOW TABLE;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near '' at line 1
MariaDB [ecomarce]> SHOW tables;
+--------------------+
| Tables_in_ecomarce |
+--------------------+
| product            |
+--------------------+
1 row in set (0.014 sec)

MariaDB [ecomarce]>

