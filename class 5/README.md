# 📘 Class 5 — NULL, AND, OR, ORDER BY, BETWEEN, IN, LIKE, LIMIT, OFFSET

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
## 🟩 AND অপারেটর  
দুটি শর্ত একসাথে সত্য হলে ডাটা দেখাবে।

```sql
SELECT * FROM TableName 
WHERE columnName = value AND columnName > value;
```

✔ ব্যবহার যখন দরকার:  
একজন কর্মচারী যার বয়স ২০ এর বেশি *এবং* ডিপার্টমেন্ট IT — এই দুই কন্ডিশন মিললে তবেই রো পাওয়া যাবে।

---

## 🟨 OR অপারেটর  
যেকোনো একটি কন্ডিশন মিললেই ডাটা দেখাবে।

```sql
SELECT * FROM TableName 
WHERE columnName = value OR columnName > value;
```

✔ ব্যবহার যখন দরকার:  
বয়স ৩০ এর বেশি **বা** ডিপার্টমেন্ট HR → যেকোনো একটি হলেই ডাটা দেখাবে।

---

## 🟧 ORDER BY (Ascending / Descending)

### ▶ Ascending Order (A → Z / ছোট → বড়)
```sql
SELECT * FROM tableName ORDER BY columnName ASC;
```

### ▶ Descending Order (Z → A / বড় → ছোট)
```sql
SELECT * FROM tableName ORDER BY columnName DESC;
```

✔ ব্যবহার যখন দরকার:  
- নাম বর্ণানুক্রমে সাজানো  
- Salary ছোট→বড়  
- সর্বোচ্চ বা সর্বনিম্ন মান বের করা

---

## 🟪 BETWEEN  
দুটি মানের **মাঝের সব রেকর্ড** খুঁজতে BETWEEN ব্যবহার হয়।

```sql
SELECT * FROM tableName 
WHERE columnName BETWEEN value1 AND value2;
```

✔ যেমন:  
১০ থেকে ২০—এই রেঞ্জের মধ্যে যত Roll আছে সব দেখাবে।

---

## 🟫 IN  
কলামের মান একটি নির্দিষ্ট লিস্টের মধ্যে আছে কিনা তা চেক করে।

```sql
SELECT * FROM TableName 
WHERE columnName IN (value1, value2, value3);
```

✔ ব্যবহার যখন দরকার:  
Roll 10, 20 বা 30 যারই হবে—তিনটিই দেখাবে।

---

## 🟩 LIKE (Pattern Matching)

LIKE দিয়ে **word-এর pattern** খোঁজা হয়।  
এখানে `%` মানে — "যেকোনো কিছু"।

### ✔ 1) value% → যাদের নাম value দিয়ে শুরু  
```sql
SELECT * FROM tableName 
WHERE columnName LIKE 'S%';
```

### ✔ 2) %value → যাদের নাম value দিয়ে শেষ  
```sql
SELECT * FROM tableName 
WHERE columnName LIKE '%r';
```

### ✔ 3) %value% → মাঝেও থাকতে পারে  
```sql
SELECT * FROM tableName 
WHERE columnName LIKE '%an%';
```

---

## 🟦 LIMIT  
কতগুলো row দেখতে চাও—সেটা নির্দিষ্ট করতে LIMIT ব্যবহার হয়।

```sql
SELECT * FROM tableName LIMIT number;
```

✔ ব্যবহার যখন দরকার:  
- প্রথম ২টি রেকর্ড  
- Top 10  
- Preview data  

---

## 🟧 OFFSET  
কয়েকটি row বাদ দিয়ে এর পরে থাকা row দেখায়।

```sql
SELECT * FROM tableName 
LIMIT limitValue OFFSET skipValue;
```

✔ উদাহরণ:  
৫টি স্কিপ করে পরের ১০টি রেকর্ড দেখাও।

---

## 🎯 Final Note  
এগুলো SQL-এর সবচেয়ে বেসিক কিন্তু সবচেয়ে বেশি ব্যবহৃত কমান্ড।  
ডেটা ফিল্টার করা, সাজানো, সার্চ করা—সবকিছুতেই এগুলো লাগে।

---
