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



<br /># 💾 MariaDB Command Session — E-commerce Database Setup

```sql
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


MariaDB [(none)]> CREATE DATABASE ecomarce;

Query OK, 1 row affected (0.001 sec)


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


MariaDB [ecomarce]> CREATE TABLE product(
    Name VARCHAR(100),
    Description VARCHAR(100),
    Price INT,
    Variant VARCHAR(100)
);

Query OK, 0 rows affected (0.094 sec)


MariaDB [ecomarce]> SHOW tables;
+--------------------+
| Tables_in_ecomarce |
+--------------------+
| product            |
+--------------------+
1 row in set (0.014 sec)


