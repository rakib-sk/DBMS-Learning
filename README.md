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
