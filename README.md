# SQL LAB PLAN — INTRODUCTION TO SQL

## 🎯 Learning Goals for This Lab

In an otherwise, predominantly NoSQL based bootcamp, this is a great opportunity to practice SQL and get introduced to it. 

By the end of today’s session, students will be able to:

* Install a SQL database engine
* Import a sample database
* Run basic SQL queries
* Understand CRUD (Create, Read, Update, Delete)
* Apply SQL fundamentals from W3Schools topics

---

## 1️⃣ STEP 1 — Install SQL on Your Machine

Students will install **XAMPP**.

### Installation Videos

* **Mac:** [https://www.youtube.com/watch?v=qst2TQRX9kw](https://www.youtube.com/watch?v=qst2TQRX9kw)
* **Windows:** [https://www.youtube.com/watch?v=aYA7B6xQC3Q](https://www.youtube.com/watch?v=aYA7B6xQC3Q)


---

## 2️⃣ STEP 2 — Import Sample Database

Steps:

1. Open **MySQL Workbench**
2. Create a new schema: `training`
3. Go to **Server → Data Import**
4. Import the provided `.sql` dump file
5. Confirm tables exist using:

```sql
SELECT * FROM books;
```

---

## 3️⃣ STEP 3 — Follow SQL Topics in Order (W3Schools)

Students follow this link:
[https://www.w3schools.com/sql/sql_intro.asp](https://www.w3schools.com/sql/sql_intro.asp)

Go through the entire articles starting from SQL Intro Upto SQL Aliases
<img width="761" height="952" alt="image" src="https://github.com/user-attachments/assets/edf11c08-0bed-491f-b1ab-2d63eeb74830" />


---

## 4️⃣ LAB ACTIVITIES — SQL BASICS

Each topic has a **Learn** + **Do** activity.

### SQL Intro + SQL Syntax

**Do:**

```sql
SELECT 'Hello SQL';
```

### SQL SELECT

```sql
SELECT title, author FROM books;
```

### SQL SELECT DISTINCT

```sql
SELECT DISTINCT genre FROM books;
```

### SQL WHERE

```sql
SELECT * FROM books WHERE genre = 'Fiction';
```

### SQL ORDER BY

```sql
SELECT * FROM books ORDER BY published_year DESC;
```

### SQL AND / OR / NOT

```sql
SELECT * FROM books
WHERE genre = 'Mystery' AND published_year > 2010;
```

### SQL INSERT

```sql
INSERT INTO books (title, author, published_year, genre)
VALUES ('New Book', 'Student', 2024, 'Fantasy');
```

### SQL UPDATE

```sql
UPDATE books
SET published_year = 2020
WHERE title = 'New Book';
```

### SQL DELETE

```sql
DELETE FROM books WHERE title = 'New Book';
```

### SQL LIMIT

```sql
SELECT * FROM books LIMIT 5;
```

### SQL Aggregate Functions

```sql
SELECT COUNT(*) AS total_books FROM books;
SELECT MIN(published_year) FROM books;
SELECT AVG(pages) FROM books;
```

### SQL LIKE

```sql
SELECT * FROM books WHERE title LIKE '%love%';
```

### SQL IN

```sql
SELECT * FROM books WHERE genre IN ('Fiction', 'Sci-Fi');
```

### SQL BETWEEN

```sql
SELECT * FROM books WHERE published_year BETWEEN 2000 AND 2010;
```

### SQL Aliases

```sql
SELECT title AS Book, published_year AS Year FROM books;
```

---

## 5️⃣ CRUD SUMMARY ACTIVITY

Students must:

* **Create:** Insert 2 new rows
* **Read:** List all rows + filter + sort
* **Update:** Update at least 1 row
* **Delete:** Delete at least 1 row

---

