# Class6 - INSERT, SELECT, ALTER TABLE

---
##Topic 
**-> INSERT, SELECT, ALTER TABLE
---

### টেবিল SELECT করা।
```sql 
SELECT * FROM databasename;
```
### নর্দিষ্ট কলাম SELECT করা।
```sql
SELECT column1,column2,.... FROLM TableName;
```

## Terminal view
```bash
MariaDB [cstustudent]>```sql SELECT Name,Roll FROM students; ```
+-------+------+
| Name  | Roll |                                                  +-------+------+
| Rakib | 50   |
+-------+------+
1 row in set (0.012 sec)

MariaDB [cstustudent]>
```
---
# নাম পরিবর্তন করা।
```sql
RENAME TABLE OldName TO newName;
```
## Terminal view
```bash
MariaDB [cstustudent]> SELECT Name,Roll FROM students;
+-------+------+
| Name  | Roll |                                                  +-------+------+
| Rakib | 50   |
+-------+------+
1 row in set (0.012 sec)

MariaDB [cstustudent]> ```sql RENAME TABLE students TO friends; ```         Query OK, 0 rows affected (0.099 sec)

MariaDB [cstustudent]> SHOW TABLES;                               +-----------------------+
| Tables_in_cstustudent |
+-----------------------+
| friends               |
+-----------------------+
1 row in set (0.013 sec)

MariaDB [cstustudent]>
```

## Table এর  পরিবর্তন করা।
---
- কোন টেবিলের কোনকিছু পরিবর্তন করতে হলে, `ALTER TABLE` ব্যবহার করতে হয়।

## কলাম যোগ করা।
-```sql ALTER TABLE TableName ADD COLUMN id INT;```

- ALTER TABLE -> টেবিল এর কোন পরিবর্তন করতে হলে লিখতে হয়।
- ADD COLUMN ->  নতুন কলাম যুক্ত করে।

## Terminal view
```bash
MariaDB [cstustudent]> ```sql ALTER TABLE friends ADD COLUMN id; ```

MariaDB [cstustudent]> ALTER TABLE friends ADD COLUMN id INT;
Query OK, 0 rows affected (0.020 sec)
Records: 0  Duplicates: 0  Warnings: 0


MariaDB [cstustudent]> INSERT INTO friends(id)
    -> VALUES(1);
Query OK, 1 row affected (0.002 sec)

MariaDB [cstustudent]> SELECT * FROM friends;
+-------+------+-------------+---------------+--------+------+
| Name  | Roll | Phone       | Email         | Gender | id   |
+-------+------+-------------+---------------+--------+------+
| Rakib | 50   | 01707899058 | rh@gamail.com | Male   | NULL |
| NULL  | NULL | NULL        | NULL          | NULL   |    1 |
+-------+------+-------------+---------------+--------+------+
2 rows in set (0.002 sec)

MariaDB [cstustudent]>
```

## কলাম DROP করা(বাদ দিয়ে দেওয়া)
```sql
ALTER TABLE TableName DROP COLUMN columnName;```


## Terminal view
```bash 

MariaDB [cstustudent]> ```sql ALTER TABLE friends DROP id; ```
Query OK, 0 rows affected (0.013 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [cstustudent]> SELECT * FROM friends;
+-------+------+-------------+---------------+--------+
| Name  | Roll | Phone       | Email         | Gender |
+-------+------+-------------+---------------+--------+
| Rakib | 50   | 01707899058 | rh@gamail.com | Male   |
| NULL  | NULL | NULL        | NULL          | NULL   |
+-------+------+-------------+---------------+--------+
2 rows in set (0.002 sec)
```

## কলাম এর Type পরিবর্তন করা।
```sql
ALTER TABLE table_name MODIFY column_name new_datatype;
```

## Terminal view
```bash 
MariaDB [cstustudent]> DESC friends;
+--------+-----------------------+------+-----+---------+-------+
| Field  | Type                  | Null | Key | Default | Extra |
+--------+-----------------------+------+-----+---------+-------+ | Name   | varchar(100)          | YES  |     | NULL    |       | | Roll   | varchar(8)            | YES  |     | NULL    |       |
| Phone  | varchar(15)           | YES  |     | NULL    |       |
| Email  | varchar(100)          | YES  |     | NULL    |       |
| Gender | enum('Male','Female') | YES  |     | NULL    |       |
+--------+-----------------------+------+-----+---------+-------+
5 rows in set (0.100 sec)

MariaDB [cstustudent]> ```sql ALTER TABLE friends MODIFY Roll INT; ```
Query OK, 2 rows affected (0.103 sec)
Records: 2  Duplicates: 0  Warnings: 0

MariaDB [cstustudent]> DESC friends;
+--------+-----------------------+------+-----+---------+-------+
| Field  | Type                  | Null | Key | Default | Extra |
+--------+-----------------------+------+-----+---------+-------+
| Name   | varchar(100)          | YES  |     | NULL    |       |
| Roll   | int(11)               | YES  |     | NULL    |       |
| Phone  | varchar(15)           | YES  |     | NULL    |       | | Email  | varchar(100)          | YES  |     | NULL    |       |
| Gender | enum('Male','Female') | YES  |     | NULL    |       | +--------+-----------------------+------+-----+---------+-------+ 5 rows in set (0.042 sec)

MariaDB [cstustudent]>
```


## Column এর অবস্থান পরিবর্তন করা।
```sql 
ALTER TABLE TableName MODIFY columnName FIRST;
```
## Terminal view
```bash
MariaDB [rt6ceo]> SELECT * FROM ceo;
+-------------+------+---------------+-----------+
| name        | id   | email         | phone     |
+-------------+------+---------------+-----------+                | Fahim vai   |    1 | abc@gmail.com | 017xxxxxx |                | Zahid vai   |    2 | xyz@gmail.com | 017abcd   |
| Zehad       |    3 | pqr@gmail.com | 018pqr    |
| Rakib       |    4 | mno@gmail.com | 018mno    |
| Sanjida apu |    5 | ijk@gmail.com | 018ijk    |
| Lamia apu   |    6 | sqr@gmail.com | 018sdk    |
+-------------+------+---------------+-----------+
6 rows in set (0.005 sec)

MariaDB [rt6ceo]>```sql ALTER TABLE ceo MODIFY id INT FIRST; ```
Query OK, 0 rows affected (0.023 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [rt6ceo]> SELECT * FROM ceo;
+------+-------------+---------------+-----------+
| id   | name        | email         | phone     |
+------+-------------+---------------+-----------+                |    1 | Fahim vai   | abc@gmail.com | 017xxxxxx |
|    2 | Zahid vai   | xyz@gmail.com | 017abcd   |                |    3 | Zehad       | pqr@gmail.com | 018pqr    |                |    4 | Rakib       | mno@gmail.com | 018mno    |
|    5 | Sanjida apu | ijk@gmail.com | 018ijk    |
|    6 | Lamia apu   | sqr@gmail.com | 018sdk    |                +------+-------------+---------------+-----------+                6 rows in set (0.001 sec)
                                                                  MariaDB [rt6ceo]>                                                 ```


## একটি কলাম অন্য আরেটি কলাম এর পরে নিয়ে যাওয়া।

```sql 
ALTER TABLE TableName MODIFY COLUMN columnName AFTER columName;
``` 

## Terminal view
```bash
MariaDB [rt6ceo]>```sql ALTER TABLE ceo MODIFY phone VARCHAR(100) AFTER ```
email;
Query OK, 0 rows affected (0.058 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [rt6ceo]> SELECT * FROM ceo;
+------+-------------+---------------+-----------+
| id   | name        | email         | phone     |
+------+-------------+---------------+-----------+
|    1 | Fahim vai   | abc@gmail.com | 017xxxxxx |
|    2 | Zahid vai   | xyz@gmail.com | 017abcd   |
|    3 | Zehad       | pqr@gmail.com | 018pqr    |
|    4 | Rakib       | mno@gmail.com | 018mno    |
|    5 | Sanjida apu | ijk@gmail.com | 018ijk    |
|    6 | Lamia apu   | sqr@gmail.com | 018sdk    |
+------+-------------+---------------+-----------+
6 rows in set (0.013 sec)

MariaDB [rt6ceo]> ```


# SELECT ব্যবহার করে MySQL-এ ডেটা কোয়েরি করা
- SELECT স্টেটমেন্ট একটি টেবিল থেকে ডেটা কোয়েরি করতে ব্যবহৃত হয়।

## Syantax:
```sql
SELECT column1, column2,.....  FROM tableName;
```

## WHERE দিয়ে filter করা।
- সমান(Eqal to)
```sql 
SELECT * FROM TableName WHERE = 1;
```
## Terminal view
```bash
MariaDB [rt6ceo]>```sql SELECT * FROM ceo WHERE id = 1; ```
+------+-----------+---------------+-----------+
| id   | name      | email         | phone     |
+------+-----------+---------------+-----------+
|    1 | Fahim vai | abc@gmail.com | 017xxxxxx |
+------+-----------+---------------+-----------+
1 row in set (0.012 sec)

MariaDB [rt6ceo]>
```

## সমান নয় (Not equal)
```sql 
SELECT * FROM TableName WHERE != 1;
```

## Terminal view
```bash
MariaDB [rt6ceo]> ```sql SELECT * FROM ceo WHERE id != 1; ```
+------+-------------+---------------+---------+
| id   | name        | email         | phone   |
+------+-------------+---------------+---------+
|    2 | Zahid vai   | xyz@gmail.com | 017abcd |
|    3 | Zehad       | pqr@gmail.com | 018pqr  |
|    4 | Rakib       | mno@gmail.com | 018mno  |
|    5 | Sanjida apu | ijk@gmail.com | 018ijk  |
|    6 | Lamia apu   | sqr@gmail.com | 018sdk  |
+------+-------------+---------------+---------+
5 rows in set (0.002 sec)

MariaDB [rt6ceo]>
```

## থেকে বড় / থেকে ছোট (Greater than/ less than)
``sql 
SELECT * FROM TableName WHERE  1 > 2; ```


