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