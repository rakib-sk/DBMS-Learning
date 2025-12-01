# Class 7: Database Keys & Auto Increment

এই README.md-তে আমরা তিনটি গুরুত্বপূর্ণ Database concept নিয়ে আলোচনা করবো: **Primary Key, Foreign Key, এবং Auto Increment।**  
এগুলো Database design-এ খুবই গুরুত্বপূর্ণ, কারণ এগুলো Data integrity এবং relationships ঠিক রাখতে সাহায্য করে।  

---

## 1. Primary Key (প্রাইমারি কী)

Primary Key হলো একটি column বা column-এর combination যা টেবিলের প্রতিটি row-এর জন্য unique থাকে। এটি **null হতে পারে না** এবং প্রতিটি row কে uniqueভাবে identify করে।  

**Example:**
```sql
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```
***এখানে student_id হলো primary key। প্রতিটি student-এর জন্য এটি unique হবে এবং পুনরায় ব্যবহার করা যাবে না।***

## 2. Foreign Key (ফরেইন কী)
- Foreign Key হলো একটি column যা অন্য table-এর primary key কে refer করে। এটি table-গুলোর মধ্যে relationship তৈরি করতে সাহায্য করে।
### Example:

```sql
CREATE TABLE Classes (
    class_id INT PRIMARY KEY,
    class_name VARCHAR(50)
);

CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    class_id INT,
    FOREIGN KEY (class_id) REFERENCES Classes(class_id)
);
```

*** Students টেবিলের class_id হলো foreign key। এটি Classes টেবিলের class_id কে refer করছে। অর্থাৎ, কোনো student যেই class-এ আছে, তা অবশ্যই Classes টেবিলে থাকা একটি class হতে হবে।***


## 3. Auto Increment (অটো ইনক্রিমেন্ট)
- Auto Increment হলো একটি column attribute যা automatically value increase করে প্রতিটি নতুন row-এর জন্য। এটি মূলত Primary Key এর সাথে ব্যবহার করা হয়।
### Example:

```sql
CREATE TABLE Students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    age INT
);
```

*** এখানে student_id auto increment হচ্ছে। প্রতিটি নতুন student insert করলে student_id স্বয়ংক্রিয়ভাবে 1, 2, 3… এর মতো বাড়বে। এতে manual ভাবে ID assign করার প্রয়োজন হয় না।***

```
## Summary Table

| Concept        | Definition & Purpose                                                                 | Example                                                                                  |
|----------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Primary Key    | প্রতিটি row কে uniqueভাবে identify করে। Null হতে পারে না।                            | `CREATE TABLE Students (student_id INT PRIMARY KEY, name VARCHAR(50), age INT);`        |
| Foreign Key    | একটি column যা অন্য table-এর primary key কে refer করে। Table-গুলোর মধ্যে relationship তৈরি করে। | `CREATE TABLE Students (student_id INT PRIMARY KEY, name VARCHAR(50), class_id INT, FOREIGN KEY (class_id) REFERENCES Classes(class_id));` |
| Auto Increment | একটি column attribute যা automatically value increase করে প্রতিটি নতুন row-এর জন্য। মূলত Primary Key-এর সাথে ব্যবহার হয়। | `CREATE TABLE Students (student_id INT PRIMARY KEY AUTO_INCREMENT, name VARCHAR(50), age INT);` |

---
```
**Note:**  
- Database design-এ এই তিনটি concept ব্যবহার করলে **data integrity, uniqueness, এবং relationships** ঠিক রাখতে সহজ হয়।


