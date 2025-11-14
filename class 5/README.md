# Class 5
## Select Null values
- SELECT * FROM TableName WHERE columnName IS NULL;

## Terminal view
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

MariaDB [empolyees]>


## AND - এর কাজ 
- SELECT * FROM TableName WHERE columnName = value AND columnName > values;

## Terminal view
MariaDB [empolyees]> SELECT * FROM employees WHERE emp_id = 2 AND salary < 100000;
+--------+---------------+------------+----------+---------------------+-------+
| emp_id | name          | department | salary   | email               | phone |
+--------+---------------+------------+----------+---------------------+-------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL  |
+--------+---------------+------------+----------+---------------------+-------+
1 row in set (0.002 sec)

MariaDB [empolyees]>


## OR - এর কাজ
- SELECT * FROM TableName WHERE columnName = value OR columnName > values;

## Terminal view

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

MariaDB [empolyees]>


## Ascending order এ সাজানো।
- SELECT * FROM tableName ORDER BY columnName ASC;


## Terminal view

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

MariaDB [empolyees]>


## Desending order - এ সাজানো
- SELECT * FROM tableName ORDER BY columnName DSC;


## Terminal view

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

## BETWEEN - এর কাজ value and value এর মাঝে যা থাকবে সব show করা।

- SELECT * FROM tableName WHERE columnName BETWEEN value AND value;

## Terminal view
MariaDB [cstustudent]> SELECT * FROM friends WHERE Roll BETWEEN 10 AND 20;
+---------+------+----------+-----------------------+
| Name    | Roll | Phone    | Email                 |
+---------+------+----------+-----------------------+
| Hanjala |   18 | 10101001 | hanjala.com@gmail.com |
| Alfi    |   15 | 101010   | alfi.com@gmail.com    |
| Raid    |   16 | 0101     | abc@gmail.com         |
+---------+------+----------+-----------------------+
3 rows in set (0.001 sec)



## IN - এর কাজ কলাম এর মধ্য value যেখানে আছে। ওটা show করা।

- SELECT * FROM TableNams WHERE ColumnName IN(value,value);


## Terminal view

MariaDB [cstustudent]> SELECT * FROM friends WHERE Roll IN("15","50");
+-------+------+-------------+--------------------+
| Name  | Roll | Phone       | Email              |
+-------+------+-------------+--------------------+
| Rakib |   50 | 01707899058 | rh@gamail.com      |
| Alfi  |   15 | 101010      | alfi.com@gmail.com |
+-------+------+-------------+--------------------+
2 rows in set (0.003 sec)

MariaDB [cstustudent]>


## Like - Pattern  মেচিং এর জন্য ব্যবহার করা হয়
- SELECT * FROM tableName WHERE columnName LIKE "value%"; - % value এর শেষ এ থাকলে কোন word এর প্রথমে ওই value থাকলে Show করবে। 

## Terminal view

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

MariaDB [empolyees]>

## % word এর প্রথমে থাকলে
- SELECT * FROM tableName WHERE columnName LIKE "%value"; - % value এর প্র এ থাকলে কোন word এর শেষ  ওই value থাকলে Show করবে। 


## Terminal view
MariaDB [empolyees]> SELECT * FROM employees WHERE name LIKE "%r";
+--------+---------------+------------+----------+---------------------+-------------+
| emp_id | name          | department | salary   | email               | phone       |
+--------+---------------+------------+----------+---------------------+-------------+
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL        |
|      7 | Sadia Noor    | IT         | 50000.00 | sadia@company.com   | 01812587463 |
|     14 | Mim Akter     | Admin      | 36000.00 | NULL                | 01586932417 |
+--------+---------------+------------+----------+---------------------+-------------+
3 rows in set (0.003 sec)

MariaDB [empolyees]>

## LIMIT - এর কাজ কত গুলো Row দেখতে চায় তা নির্দিষ্ট করে দেখায়।
- SELECT * FROM tableName LIMIT value;  - value অনুযায়ী Row show করবে।

## Terminal view
MariaDB [empolyees]> SELECT * FROM employees LIMIT 2;
+--------+---------------+------------+----------+---------------------+-------------+
| emp_id | name          | department | salary   | email               | phone       |
+--------+---------------+------------+----------+---------------------+-------------+
|      1 | Rakib Hossain | IT         | 45000.00 | rakib@company.com   | 01828315879 |
|      2 | Sanjida Akter | HR         | 40000.00 | sanjida@company.com | NULL        |
+--------+---------------+------------+----------+---------------------+-------------+
2 rows in set (0.001 sec)
MariaDB [empolyees]>

## OFFSET - সারি বাদ দিয়ে  পরের সারি Show করে।
- SELECT * FROM TableName LIMIT value OFFSET value - 
