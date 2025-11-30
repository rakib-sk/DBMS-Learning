# DBMS-Learning
# 🏫 Class 1 — Introduction to DBMS

## 1️⃣ Termux Setup for Database

- Termux ইন্সটল করো  
- MariaDB বা MySQL প্যাকেজ ইন্সটল করো:  
```bash
pkg install mariadb
```
- সার্ভার স্টার্ট করো:  
```bash
mysqld_safe &
```
- MariaDB এ প্রবেশ করো:  
```bash
mysql -u root
```

> এখন তুমি Database তৈরি এবং SQL commands ব্যবহার করতে প্রস্তুত।  

---

## 2️⃣ What is DBMS?

**DBMS (Database Management System)** → এমন software যা ডাটাকে **store, manage এবং organize** করে।  

### Key Points:
- ডাটা সংরক্ষণ করে **efficient এবং secure** ভাবে।  
- SQL ব্যবহার করে ডাটা **query এবং manipulate** করা যায়।  
- উদাহরণ: MySQL, MariaDB, PostgreSQL, Oracle DB  

---

## 3️⃣ Why DBMS?

- ডাটার **consistency** ও **integrity** বজায় রাখে  
- ডাটার **security** নিশ্চিত করে  
- সহজে **search, update, delete** করা যায়  

> ✅ DBMS শেখার মাধ্যমে তুমি Structured Data handle করতে পারবে এবং real-world applications এ কাজ করতে পারবে।


# 🏫 Class 2 — Step by Step Database Tutorial

Step by Step গাইড আমাদের **Database এবং Table তৈরি** করার জন্য।  

---

## 📝 আমাদের কাজ

### 1️⃣ Database তৈরি করা
**Cmd:**  
```sql
SHOW databases;
```
> এই কমান্ড দিয়ে আগে থেকে থাকা ডাটাবেসগুলো দেখা যায়।  

**Cmd (নতুন Database তৈরি করার জন্য):**  
```sql
CREATE DATABASE DatabaseName;
```
> এখানে `DatabaseName` এর জায়গায় নিজের ডাটাবেসের নাম ব্যবহার করবে।  

---

### 2️⃣ Database-এ প্রবেশ করা
**Cmd:**  
```sql
USE DatabaseName;
```
> এটি তোমাকে নির্দিষ্ট ডাটাবেসে প্রবেশ করাবে।  

---

### 3️⃣ টেবিল তৈরি করা
**Cmd:**  
```sql
CREATE TABLE product(
    Name VARCHAR(100),
    Description VARCHAR(100),
    Price INT,
    Variant VARCHAR(100)
);
```
> এই কমান্ড দিয়ে `product` নামে একটি টেবিল তৈরি হবে।  

**Cmd (টেবিলগুলো দেখানোর জন্য):**  
```sql
SHOW TABLES;
```
> এই কমান্ড দিয়ে ডাটাবেসের সব টেবিল দেখা যাবে।  

---

## 🔍 Column Explanation

- **Name**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের নাম সংরক্ষণ করে।  

- **Description**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের বিস্তারিত বিবরণ।  

- **Price**  
  - টাইপ: `INT`  
  - ব্যাখ্যা: প্রোডাক্টের দাম।  

- **Variant**  
  - টাইপ: `VARCHAR(100)`  
  - ব্যাখ্যা: প্রোডাক্টের ভ্যারিয়েন্ট, যেমন রঙ বা সাইজ।  

---

## 💡 Tips
- সব SQL কমান্ড **`sql` কোড ব্লক**-এ রাখলে GitHub README-তে সুন্দর দেখাবে।  
- ডাটাবেস নাম ও টেবিল নাম ছোট হাতের অক্ষরে রাখলে কোনো সমস্যা হবে না।  
- প্রয়োজনে `ALTER TABLE` দিয়ে Column যোগ বা পরিবর্তন করা যেতে পারে।  

---

🎯 **Summary Steps**  
1. `SHOW databases` → ডাটাবেস দেখা  
2. `CREATE DATABASE` → নতুন ডাটাবেস তৈরি  
3. `USE` → ডাটাবেসে প্রবেশ  
4. `CREATE TABLE` → টেবিল তৈরি  
5. `SHOW TABLES` → টেবিলগুলো দেখো  

> এবার তুমি নিজের E-commerce Database তৈরি করতে প্রস্তুত! 🛒💻


# 💻 Class 3 — Data Types & Binary Numbers

---

## 📘 Topic  
**→ Datatype, Binary Number, Table Creation & Data Insertion**

---

## 🧠 Data Types in SQL

**1️⃣ Numeric Types**  
- `INT` → পূর্ণসংখ্যা  
- `FLOAT`, `DOUBLE` → দশমিক সংখ্যা  

**2️⃣ Date & Time Types**  
- `DATE` → শুধুমাত্র তারিখ  
- `DATETIME` → তারিখ ও সময় দুটোই  

**3️⃣ String Types**  
- `CHAR`, `VARCHAR` → টেক্সট সংরক্ষণের জন্য  

---

## ⚙️ Binary Number System

Binary Number → 0 এবং 1 দ্বারা গঠিত হয়  
> উদাহরণ: `1010` (Binary) = 10 (Decimal)

---

## 🧩 Make Student Database

### ✅ Step 1: Create Database
```sql
CREATE DATABASE cstustudent;
USE cstustudent;
```

### ✅ Step 2: Create Table
```sql
CREATE TABLE students(
    Name VARCHAR(100),
    Roll VARCHAR(8),
    Phone VARCHAR(15),
    Email VARCHAR(100),
    Gender ENUM('Male','Female')
);
```

---

## 💻 Terminal View

```bash
MariaDB [(none)]> CREATE database cstustudent;
Query OK, 1 row affected (0.011 sec)

MariaDB [(none)]> SHOW databases;
+--------------------+
| Database           |
+--------------------+
| cstustudent        |
| ecomarce           |
| ecommerce          |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test               |
| testdb             |
+--------------------+
9 rows in set (0.028 sec)

MariaDB [cstustudent]> CREATE TABLE students(
    -> Name VARCHAR(100),
    -> Roll VARCHAR(8),
    -> Phone VARCHAR(15),
    -> Email VARCHAR(100),
    -> Gender ENUM('Male', 'Female')
    -> );
Query OK, 0 rows affected (0.090 sec)
```

---

## 🔎 How to Show Table?

**Command:**
```sql
DESC students;
```

**Terminal View:**
```bash
+--------+-----------------------+------+-----+---------+-------+
| Field  | Type                  | Null | Key | Default | Extra |
+--------+-----------------------+------+-----+---------+-------+
| Name   | varchar(100)          | YES  |     | NULL    |       |
| Roll   | varchar(8)            | YES  |     | NULL    |       |
| Phone  | varchar(15)           | YES  |     | NULL    |       |
| Email  | varchar(100)          | YES  |     | NULL    |       |
| Gender | enum('Male','Female') | YES  |     | NULL    |       |
+--------+-----------------------+------+-----+---------+-------+
5 rows in set (0.108 sec)
```

---

## ✍️ Insert Data into Table

### Syntax:
```sql
INSERT INTO students(Name, Roll, Phone, Email, Gender)
VALUES ("Rakib", "50", "01707899058", "rh@gmail.com", "Male");
```

---

## 👁️ Show Data

### Syntax:
```sql
SELECT * FROM students;
```

### Terminal View:
```bash
+-------+------+-------------+---------------+--------+
| Name  | Roll | Phone       | Email         | Gender |
+-------+------+-------------+---------------+--------+
| Rakib | 50   | 01707899058 | rh@gmail.com  | Male   |
+-------+------+-------------+---------------+--------+
1 row in set (0.022 sec)
```

---

## 🧠 Task 1 — CEO Table Practice

### Command:
```sql
INSERT INTO ceo (id, name, email, phone)
VALUES
(1, "Fahim vai", "abc@gmail.com", "017xxxxxx"),
(2, "Zahid vai", "xyz@gmail.com", "017abcd"),
(3, "Zehad", "pqr@gmail.com", "018pqr"),
(4, "Rakib", "mno@gmail.com", "018mno"),
(5, "Sanjida apu", "ijk@gmail.com", "018ijk"),
(6, "Lamia apu", "sqr@gmail.com", "018sdk");
```

### Terminal View:
```bash
SELECT * FROM ceo;
+-------------+------+---------------+-----------+
| name        | id   | email         | phone     |
+-------------+------+---------------+-----------+
| Fahim vai   | 1    | abc@gmail.com | 017xxxxxx |
| Zahid vai   | 2    | xyz@gmail.com | 017abcd   |
| Zehad       | 3    | pqr@gmail.com | 018pqr    |
| Rakib       | 4    | mno@gmail.com | 018mno    |
| Sanjida apu | 5    | ijk@gmail.com | 018ijk    |
| Lamia apu   | 6    | sqr@gmail.com | 018sdk    |
+-------------+------+---------------+-----------+
6 rows in set (0.002 sec)
```

---

> ✅ **Summary:**  
এই Class-এ আমরা শিখেছি —  
- SQL Data Types  
- Binary Number Basics  
- Database, Table Creation  
- Data Insert এবং Show করা  

---

> ✍️ **By Rakib**  
_Made with ❤️ for DBMS Practice_
>
# 📘 Class 4 — INSERT, SELECT, ALTER TABLE

---

## 🧩 Topic
**INSERT**, **SELECT**, **ALTER TABLE**

---

### 🔹 সব কলাম SELECT করা

```sql
SELECT * FROM TableName;
```

**Example:**
```sql
SELECT * FROM students;
```

---

### 🔹 নির্দিষ্ট কলাম SELECT করা

```sql
SELECT column1, column2, ... FROM TableName;
```

**Example:**
```sql
SELECT Name, Roll FROM students;
```

---

### 🖥️ Terminal View

```
MariaDB [cstustudent]> SELECT Name, Roll FROM students;
+-------+------+
| Name  | Roll |
+-------+------+
| Rakib | 50   |
+-------+------+
1 row in set (0.012 sec)
```

---

## 🔄 টেবিলের নাম পরিবর্তন করা

```sql
RENAME TABLE OldName TO NewName;
```

**Example:**
```sql
RENAME TABLE students TO student_data;
```

---

### 🖥️ Terminal View

```
MariaDB [cstustudent]> RENAME TABLE students TO student_data;
Query OK, 0 rows affected (0.015 sec)

MariaDB [cstustudent]> SHOW TABLES;
+----------------------+
| Tables_in_cstustudent |
+----------------------+
| student_data          |
+----------------------+
1 row in set (0.002 sec)
```

---

## ✏️ ALTER TABLE — কলাম পরিবর্তন, যোগ বা বাদ দেওয়া

### 🔹 নতুন কলাম যোগ করা

```sql
ALTER TABLE student_data ADD COLUMN Address VARCHAR(100);
```

### 🔹 কলামের নাম পরিবর্তন করা

```sql
ALTER TABLE student_data CHANGE COLUMN Roll StudentRoll VARCHAR(10);
```

### 🔹 কলাম মুছে ফেলা

```sql
ALTER TABLE student_data DROP COLUMN Address;
```

---

## ✅ Summary

এই ক্লাসে শিখেছো:
- SELECT দিয়ে ডাটা দেখা  
- নির্দিষ্ট কলাম বাছাই করা  
- টেবিল rename করা  
- ALTER TABLE দিয়ে column add, rename বা delete করা  

---

> 💡 **Tip:**  
> Practice করার সময় সব কমান্ড `;` দিয়ে শেষ করবে।  
> ভুল spelling যেমন `FROLM` বা `databese` দিলে syntax error আসবে।
>
> # 📘 Class 5 — NULL, AND, OR, ORDER BY, BETWEEN, IN, LIKE, LIMIT, OFFSET

---

## 🔹 NULL Values খুঁজে বের করা
```sql
SELECT * FROM TableName WHERE columnName IS NULL;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees WHERE phone IS NULL;
+--------+---------------+------------+----------+---------------------+-------+
| emp_id | name          | department | salary   | email               | phone |
+--------+---------------+------------+----------+---------------------+-------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL  |
|      6 | Rafi Ahmed    | Marketing  | 35000.00 | rafi@company.com    | NULL  |
|      8 | Sohan Khan    | Finance    | 42000.00 | NULL                | NULL  |
|     13 | Hasan Mahmud  | Marketing  | 37000.00 | hasan@company.com   | NULL  |
|     17 | Riyad Hossain | IT         | 46000.00 | NULL                | NULL  |
|     19 | Sabbir Khan   | Security   | 28000.00 | sabbir@company.com  | NULL  |
+--------+---------------+------------+----------+---------------------+-------+
6 rows in set (0.014 sec)
```

---

## 🔹 AND — দুটি শর্তই সত্য হলে Row দেখাবে
```sql
SELECT * FROM TableName WHERE column1 = value AND column2 > value;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees WHERE emp_id = 2 AND salary < 100000;
+--------+---------------+------------+----------+---------------------+-------+
| emp_id | name          | department | salary   | email               | phone |
+--------+---------------+------------+----------+---------------------+-------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL  |
+--------+---------------+------------+----------+---------------------+-------+
1 row in set (0.002 sec)
```

---

## 🔹 OR — যেকোনো একটি শর্ত সত্য হলেই Row দেখাবে
```sql
SELECT * FROM TableName WHERE column1 = value OR column2 > value;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees WHERE emp_id = 2 OR salary < 100000;
+--------+----------------+------------+----------+---------------------+-------------+
| emp_id | name           | department | salary   | email               | phone       |
+--------+----------------+------------+----------+---------------------+-------------+
|      1 | Rakib Hossain  | IT         | 45000.00 | rakib@company.com   | 01828315879 |
|      2 | Sanjida Akter  | HR         | 40000.00 | sanjida@company.com | NULL        |
|      4 | Tania Rahman   | NULL       | 38000.00 | tania@company.com   | 01692587410 |
|      5 | Nafis Alam     | IT         | 47000.00 | NULL                | 01523647890 |
|      6 | Rafi Ahmed     | Marketing  | 35000.00 | rafi@company.com    | NULL        |
|      7 | Sadia Noor     | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|      8 | Sohan Khan     | Finance    | 42000.00 | NULL                | NULL        |
|      9 | Nusrat Jahan   | Admin      | 39000.00 | nusrat@company.com  | 01736985241 |
|     10 | Tuhin Roy      | Security   | 25000.00 | NULL                | 01865987541 |
|     11 | Shila Parvin   | HR         | 41000.00 | shila@company.com   | 01787458965 |
|     13 | Hasan Mahmud   | Marketing  | 37000.00 | hasan@company.com   | NULL        |
|     14 | Mim Akter      | Admin      | 36000.00 | NULL                | 01586932417 |
|     15 | Kamal Uddin    | NULL       | 34000.00 | kamal@company.com   | 01745896321 |
|     16 | Jannat Ferdous | Finance    | 42000.00 | jannat@company.com  | 01894561278 |
|     17 | Riyad Hossain  | IT         | 46000.00 | NULL                | NULL        |
|     19 | Sabbir Khan    | Security   | 28000.00 | sabbir@company.com  | NULL        |
|     20 | Arif Hasan     | Marketing  | 37000.00 | NULL                | 01985471236 |
+--------+----------------+------------+----------+---------------------+-------------+
17 rows in set (0.005 sec)
```

---

## 🔹 ASC — নাম অনুযায়ী উপরে থেকে নিচে সাজানো
```sql
SELECT * FROM tableName ORDER BY columnName ASC;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees ORDER BY name ASC;
+--------+----------------+------------+----------+---------------------+-------------+
| emp_id | name           | department | salary   | email               | phone       |
+--------+----------------+------------+----------+---------------------+-------------+
|     20 | Arif Hasan     | Marketing  | 37000.00 | NULL                | 01985471236 |
|     13 | Hasan Mahmud   | Marketing  | 37000.00 | hasan@company.com   | NULL        |
|     12 | Imran Ali      | IT         |     NULL | imran@company.com   | 01658963214 |
|     16 | Jannat Ferdous | Finance    | 42000.00 | jannat@company.com  | 01894561278 |
|     15 | Kamal Uddin    | NULL       | 34000.00 | kamal@company.com   | 01745896321 |
|      3 | Mahin Islam    | Finance    |     NULL | mahin@company.com   | 01725648912 |
|     14 | Mim Akter      | Admin      | 36000.00 | NULL                | 01586932417 |
|      5 | Nafis Alam     | IT         | 47000.00 | NULL                | 01523647890 |
|      9 | Nusrat Jahan   | Admin      | 39000.00 | nusrat@company.com  | 01736985241 |
|      6 | Rafi Ahmed     | Marketing  | 35000.00 | rafi@company.com    | NULL        |
|      1 | Rakib Hossain  | IT         | 45000.00 | rakib@company.com   | 01828315879 |
|     17 | Riyad Hossain  | IT         | 46000.00 | NULL                | NULL        |
|     19 | Sabbir Khan    | Security   | 28000.00 | sabbir@company.com  | NULL        |
|      7 | Sadia Noor     | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|      2 | Sanjida Akter  | HR         | 40000.00 | sanjida@company.com | NULL        |
|     11 | Shila Parvin   | HR         | 41000.00 | shila@company.com   | 01787458965 |
|      8 | Sohan Khan     | Finance    | 42000.00 | NULL                | NULL        |
|      4 | Tania Rahman   | NULL       | 38000.00 | tania@company.com   | 01692587410 |
|     18 | Toma Rahman    | HR         |     NULL | toma@company.com    | 01852369874 |
|     10 | Tuhin Roy      | Security   | 25000.00 | NULL                | 01865987541 |
+--------+----------------+------------+----------+---------------------+-------------+
20 rows in set (0.009 sec)
```

---

## 🔹 DESC — নাম অনুযায়ী নিচ থেকে উপরে সাজানো
```sql
SELECT * FROM tableName ORDER BY columnName DESC;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees ORDER BY name DESC;
+--------+----------------+------------+----------+---------------------+-------------+
| emp_id | name           | department | salary   | email               | phone       |
+--------+----------------+------------+----------+---------------------+-------------+
|     10 | Tuhin Roy      | Security   | 25000.00 | NULL                | 01865987541 |
|     18 | Toma Rahman    | HR         |     NULL | toma@company.com    | 01852369874 |
|      4 | Tania Rahman   | NULL       | 38000.00 | tania@company.com   | 01692587410 |
|      8 | Sohan Khan     | Finance    | 42000.00 | NULL                | NULL        |
|     11 | Shila Parvin   | HR         | 41000.00 | shila@company.com   | 01787458965 |
|      2 | Sanjida Akter  | HR         | 40000.00 | sanjida@company.com | NULL        |
|      7 | Sadia Noor     | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|     19 | Sabbir Khan    | Security   | 28000.00 | sabbir@company.com  | NULL        |
|     17 | Riyad Hossain  | IT         | 46000.00 | NULL                | NULL        |
|      1 | Rakib Hossain  | IT         | 45000.00 | rakib@company.com   | 01828315879 |
|      6 | Rafi Ahmed     | Marketing  | 35000.00 | rafi@company.com    | NULL        |
|      9 | Nusrat Jahan   | Admin      | 39000.00 | nusrat@company.com  | 01736985241 |
|      5 | Nafis Alam     | IT         | 47000.00 | NULL                | 01523647890 |
|     14 | Mim Akter      | Admin      | 36000.00 | NULL                | 01586932417 |
|      3 | Mahin Islam    | Finance    |     NULL | mahin@company.com   | 01725648912 |
|     15 | Kamal Uddin    | NULL       | 34000.00 | kamal@company.com   | 01745896321 |
|     16 | Jannat Ferdous | Finance    | 42000.00 | jannat@company.com  | 01894561278 |
|     12 | Imran Ali      | IT         |     NULL | imran@company.com   | 01658963214 |
|     13 | Hasan Mahmud   | Marketing  | 37000.00 | hasan@company.com   | NULL        |
|     20 | Arif Hasan     | Marketing  | 37000.00 | NULL                | 01985471236 |
+--------+----------------+------------+----------+---------------------+-------------+
20 rows in set (0.003 sec)
```

---

## 🔹 BETWEEN — দুটি মানের মাঝের সব Values দেখাবে
```sql
SELECT * FROM tableName WHERE columnName BETWEEN value1 AND value2;
```

### 🖥️ Terminal View
```
MariaDB [cstustudent]> SELECT * FROM friends WHERE Roll BETWEEN 10 AND 20;
+---------+------+----------+-----------------------+
| Name    | Roll | Phone    | Email                 |
+---------+------+----------+-----------------------+
| Hanjala |   18 | 10101001 | hanjala.com@gmail.com |
| Alfi    |   15 | 101010   | alfi.com@gmail.com    |
| Raid    |   16 | 0101     | abc@gmail.com         |
+---------+------+----------+-----------------------+
3 rows in set (0.001 sec)
```

---

## 🔹 IN — নির্দিষ্ট কয়েকটি Value মিলে গেলে Row দেখাবে
```sql
SELECT * FROM TableName WHERE columnName IN (value1, value2);
```

### 🖥️ Terminal View
```
MariaDB [cstustudent]> SELECT * FROM friends WHERE Roll IN ("15", "50");
+-------+------+-------------+--------------------+
| Name  | Roll | Phone       | Email              |
+-------+------+-------------+--------------------+
| Rakib |   50 | 01707899058 | rh@gamail.com      |
| Alfi  |   15 | 101010      | alfi.com@gmail.com |
+-------+------+-------------+--------------------+
2 rows in set (0.003 sec)
```

---

## 🔹 LIKE — Pattern Matching
```sql
SELECT * FROM tableName WHERE columnName LIKE "value%";   -- value দিয়ে শুরু
SELECT * FROM tableName WHERE columnName LIKE "%value";   -- value দিয়ে শেষ
```

### 🖥️ LIKE "S%" Example
```
MariaDB [empolyees]> SELECT * FROM employees WHERE name LIKE "S%";
+--------+---------------+------------+----------+---------------------+-------------+
| emp_id | name          | department | salary   | email               | phone       |
+--------+---------------+------------+----------+---------------------+-------------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL        |
|      7 | Sadia Noor    | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|      8 | Sohan Khan    | Finance    | 42000.00 | NULL                | NULL        |
|     11 | Shila Parvin  | HR         | 41000.00 | shila@company.com   | 01787458965 |
|     19 | Sabbir Khan   | Security   | 28000.00 | sabbir@company.com  | NULL        |
+--------+---------------+------------+----------+---------------------+-------------+
5 rows in set (0.039 sec)
```

### 🖥️ LIKE "%r" Example
```
MariaDB [empolyees]> SELECT * FROM employees WHERE name LIKE "%r";
+--------+---------------+------------+----------+---------------------+-------------+
| emp_id | name          | department | salary   | email               | phone       |
+--------+---------------+------------+----------+---------------------+-------------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL        |
|      7 | Sadia Noor    | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|     14 | Mim Akter     | Admin      | 36000.00 | NULL                | 01586932417 |
+--------+---------------+------------+----------+---------------------+-------------+
3 rows in set (0.003 sec)
```

---

## 🔹 LIMIT — কতটি Row দেখাবে
```sql
SELECT * FROM tableName LIMIT value;
```

### 🖥️ Terminal View
```
MariaDB [empolyees]> SELECT * FROM employees LIMIT 2;
+--------+---------------+------------+----------+---------------------+-------------+
| emp_id | name          | department | salary   | email               | phone       |
+--------+---------------+------------+----------+---------------------+-------------+
|      1 | Rakib Hossain | IT         | 45000.00 | rakib@company.com   | 01828315879 |
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL        |
+--------+---------------+------------+----------+---------------------+-------------+
2 rows in set (0.001 sec)
```

---

## 🔹 OFFSET — প্রথম X Row বাদ দিয়ে পরের Row দেখাবে
```sql
SELECT * FROM tableName LIMIT value OFFSET value;
```

---

## ✅ Summary
এই ক্লাসে শিখেছো:
- NULL filtering  
- AND / OR conditions  
- ASC / DESC sorting  
- BETWEEN / IN filtering  
- LIKE দিয়ে pattern matching  
- LIMIT ও OFFSET  

---


# Class 7: Database Keys & Auto Increment

এই README.md-তে আমরা তিনটি গুরুত্বপূর্ণ Database concept নিয়ে আলোচনা করবো: **Primary Key, Foreign Key, এবং Auto Increment।**  
এগুলো Database design-এ খুবই গুরুত্বপূর্ণ, কারণ এগুলো Data integrity এবং relationships ঠিক রাখতে সাহায্য করে।  

---

## Summary Table

| Concept        | Definition & Purpose                                                                 | Example                                                                                  |
|----------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Primary Key    | প্রতিটি row কে uniqueভাবে identify করে। Null হতে পারে না।                            | `CREATE TABLE Students (student_id INT PRIMARY KEY, name VARCHAR(50), age INT);`        |
| Foreign Key    | একটি column যা অন্য table-এর primary key কে refer করে। Table-গুলোর মধ্যে relationship তৈরি করে। | `CREATE TABLE Students (student_id INT PRIMARY KEY, name VARCHAR(50), class_id INT, FOREIGN KEY (class_id) REFERENCES Classes(class_id));` |
| Auto Increment | একটি column attribute যা automatically value increase করে প্রতিটি নতুন row-এর জন্য। মূলত Primary Key-এর সাথে ব্যবহার হয়। | `CREATE TABLE Students (student_id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(50), age INT);` |

---

**Note:**  
Database design-এ এই তিনটি concept ব্যবহার করলে **data integrity, uniqueness, এবং relationships** ঠিক রাখতে সহজ হয়।
