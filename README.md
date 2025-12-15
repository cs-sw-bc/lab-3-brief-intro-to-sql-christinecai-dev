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

primary key: its id
foreign key: reference key

Mongo.DB: books.find()-- return all the books

SQL (queries are statement)-- select (find) * (all columns in a table) from books; (display all columns from the books table)
-need all actors' first name: select first_name from actor;
-use control enter
-SELECT * FROM `actor`;
-SELECT first_name, last_name FROM `actor`; or jsut actor

actor.find({name:'Johny'});

select * from actor where first_name = 'Johny';



records are rows

* Select statement
- SELECT address FROM address //return address from the address table
- SELECT column1, column2, ...FROM table_name;
- SELECT * FROM table_name //return all columns


* Select distinct statement: The SELECT DISTINCT statement is used to return only distinct (different) values.
- SELECT DISTINCT Country FROM Customers;
- SELECT COUNT(DISTINCT Country) FROM Customers;//return the number of different countries


* Where clause:  extract only those records that fulfill a specified condition.
SELECT column1, column2, ...
FROM table_name
WHERE condition;

SELECT city
FROM city
WHERE city = 'Aden';

=	Equal	
>	Greater than	
<	Less than	
>=	Greater than or equal	
<=	Less than or equal	
<>	Not equal. Note: In some versions of SQL this operator may be written as !=	
BETWEEN	Between a certain range	
LIKE	Search for a pattern	
IN	To specify multiple possible values for a column


* Order by:  sort the result-set in ascending or descending order
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

SELECT * FROM payment
ORDER BY amount DESC;

- The ORDER BY keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.

SELECT * FROM Products
ORDER BY Price DESC;

-For string values the ORDER BY keyword will order alphabetically:
SELECT * FROM Products
ORDER BY ProductName;

-The following SQL statement selects all customers from the "Customers" table, sorted by the "Country" and the "CustomerName" column. This means that it orders by Country, but if some rows have the same Country, it orders them by CustomerName:
SELECT * FROM Customers
ORDER BY Country, CustomerName;

-The following SQL statement selects all customers from the "Customers" table, sorted ascending by the "Country" and descending by the "CustomerName" column:
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;


* And operator
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

SELECT *
FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
e.g. Select all customers from Spain that starts with the letter 'G':

Select all Spanish customers that starts with either "G" or "R":
SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');


* OR operator
- Select all customers from Germany or Spain:
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

SELECT * FROM Customers
WHERE City = 'Berlin' OR CustomerName LIKE 'G%' OR Country = 'Norway';

* NOT operator
- Select only the customers that are NOT from Spain:

SELECT * FROM Customers
WHERE NOT Country = 'Spain';

SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

Select customers that does not start with the letter 'A':
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'A%';

Select customers with a customerID not between 10 and 60:
SELECT * FROM Customers
WHERE CustomerID NOT BETWEEN 10 AND 60;

* INSERT INTO
- The INSERT INTO statement is used to insert new records in a table.
- Specify both the column names and the values to be inserted:

INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

- If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the INSERT INTO syntax would be as follows:

INSERT INTO table_name
VALUES (value1, value2, value3, ...);

-To insert multiple rows of data, we use the same INSERT INTO statement, but with multiple values

INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'),
('Greasy Burger', 'Per Olsen', 'Gateveien 15', 'Sandnes', '4306', 'Norway'),
('Tasty Tee', 'Finn Egan', 'Streetroad 19B', 'Liverpool', 'L1 0AA', 'UK');


* Null value
- A field with a NULL value is a field with no value.
SELECT column_names
FROM table_name
WHERE column_name IS NULL;

SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;


* Update statement

UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

- WHERE clause specifies which record(s) that should be updated

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

The following SQL statement will update the ContactName to "Juan" for all records where country is "Mexico":

UPDATE Customers
SET ContactName='Juan'
WHERE Country='Mexico';


* Delete statement

- DELETE FROM table_name WHERE condition;

DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';

- possible to delete all rows in a table without deleting the table

DELETE FROM table_name;

- delete the table completely

DROP TABLE Customers;


* Select Top clause

- used to specify the number of records to return.

- Select only the first 3 records of the Customers table:
SELECT TOP 3 * FROM Customers;

SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;

- Select the first 3 records of the Customers table:
SELECT * FROM Customers
LIMIT 3;

-the following SQL statement selects the first 50% of the records from the "Customers" table
SELECT TOP 50 PERCENT * FROM Customers;

-The following SQL statement selects the first three records from the "Customers" table, where the country is "Germany"
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;

-Sort the result reverse alphabetically by CustomerName, and return the first 3 records:
SELECT * FROM Customers
ORDER BY CustomerName DESC
LIMIT 3;


* Aggregate functions
- MIN() - returns the smallest value within the selected column
SELECT MIN(Price)
FROM Products;

SELECT MIN(column_name)
FROM table_name
WHERE condition;

- MAX() - returns the largest value within the selected column
SELECT MAX(Price)
FROM Products;

SELECT MAX(column_name)
FROM table_name
WHERE condition;

-When you use MIN() or MAX(), the returned column will not have a descriptive name. To give the column a descriptive name, use the AS keyword:
SELECT MIN(Price) AS SmallestPrice
FROM Products;

-Here we use the MIN() function and the GROUP BY clause, to return the smallest price for each category in the Products table:
SELECT MIN(Price) AS SmallestPrice, CategoryID
FROM Products
GROUP BY CategoryID;




- COUNT() - returns the number of rows in a set
 total number of rows in the Products table:

SELECT COUNT(*)
FROM Products;

SELECT COUNT(column_name)
FROM table_name
WHERE condition;

SELECT COUNT(ProductID)
FROM Products
WHERE Price > 20;

SELECT COUNT(DISTINCT Price)
FROM Products;

Name the column "Number of records":
SELECT COUNT(*) AS [Number of records]
FROM Products;

Here we use the COUNT() function and the GROUP BY clause, to return the number of records for each category in the Products table:
SELECT COUNT(*) AS [Number of records], CategoryID
FROM Products
GROUP BY CategoryID;



- SUM() - returns the total sum of a numerical colum
SELECT SUM(column_name)
FROM table_name
WHERE condition;

SELECT SUM(Quantity)
FROM OrderDetails
WHERE ProductId = 11;

SELECT SUM(Quantity) AS total
FROM OrderDetails;

SELECT OrderID, SUM(Quantity) AS [Total Quantity]
FROM OrderDetails
GROUP BY OrderID;

SELECT SUM(Quantity * 10)
FROM OrderDetails;


- AVG() - returns the average value of a numerical column
SELECT AVG(column_name)
FROM table_name
WHERE condition;

SELECT AVG(Price)
FROM Products
WHERE CategoryID = 1;

SELECT AVG(Price) AS [average price]
FROM Products;

Return all products with a higher price than the average price:
SELECT * FROM Products
WHERE price > (SELECT AVG(price) FROM Products);

SELECT AVG(Price) AS AveragePrice, CategoryID
FROM Products
GROUP BY CategoryID;


* Like operator
- The percent sign % represents zero, one, or multiple characters
- The underscore sign _ represents one, single character

- Select all customers that starts with the letter "a":
SELECT * FROM Customers
WHERE CustomerName LIKE 'a%';

SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;

- Return all customers from a city that starts with 'L' followed by one wildcard character, then 'nd' and then two wildcard characters:
SELECT * FROM Customers
WHERE city LIKE 'L_nd__';

-The % wildcard represents any number of characters, even zero characters.


* Wildcards
%	Represents zero or more characters
_	Represents a single character
[]	Represents any single character within the brackets *
^	Represents any character not in the brackets *
-	Represents any single character within the specified range *
{}	Represents any escaped character *

- The [] wildcard returns a result if any of the characters inside gets a match.
Return all customers starting with either "b", "s", or "p":
SELECT * FROM Customers
WHERE CustomerName LIKE '[bsp]%';

- The - wildcard allows you to specify a range of characters inside the [] wildcard.
Return all customers starting with "a", "b", "c", "d", "e" or "f":
SELECT * FROM Customers
WHERE CustomerName LIKE '[a-f]%';


* IN operator
- The IN operator allows you to specify multiple values in a WHERE clause.
Return all customers from 'Germany', 'France', or 'UK'
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');

SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);

- By using the NOT keyword in front of the IN operator, you return all records that are NOT any of the values in the list.
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');

- In (Select): You can also use IN with a subquery in the WHERE clause.

With a subquery you can return all records from the main query that are present in the result of the subquery.

SELECT * FROM Customers
WHERE CustomerID IN (SELECT CustomerID FROM Orders);

Return all customers that have NOT placed any orders in the Orders table:
SELECT * FROM Customers
WHERE CustomerID NOT IN (SELECT CustomerID FROM Orders);


* Between operator
- The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.
- The BETWEEN operator is inclusive: begin and end values are included. 

SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;

SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

- To display the products outside the range of the previous example, use NOT BETWEEN:
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;

- The following SQL statement selects all products with a price between 10 and 20. In addition, the CategoryID must be either 1,2, or 3:

SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID IN (1,2,3);

- The following SQL statement selects all products with a ProductName alphabetically between Carnarvon Tigers and Mozzarella di Giovanni:

SELECT * FROM Products
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'
ORDER BY ProductName;

SELECT * FROM Orders
WHERE OrderDate BETWEEN #07/01/1996# AND #07/31/1996#;


* Aliases

- An alias is created with the AS keyword.
SELECT CustomerID AS ID
FROM Customers;

SELECT CustomerID ID
FROM Customers;

SELECT column_name AS alias_name
FROM table_name;

SELECT column_name(s)
FROM table_name AS alias_name;

- If you want your alias to contain one or more spaces, like "My Great Products", surround your alias with square brackets or double quotes.

Using [square brackets] for aliases with space characters:
SELECT ProductName AS [My Great Products]
FROM Products;

Using "double quotes" for aliases with space characters:
SELECT ProductName AS "My Great Products"
FROM Products;

The following SQL statement creates an alias named "Address" that combine four columns (Address, PostalCode, City and Country):

SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;

Refer to the Customers table as Persons instead:
SELECT * FROM Customers AS Persons;


SQL Join

* Inner Join
- The INNER JOIN keyword returns only rows with a match in both tables

SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

* Left Join
- The LEFT JOIN keyword returns all records from the left table (table1), and the matching records from the right table (table2)
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;

* Right Join
- The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records from the left table (table1)

SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;

* Full Outer Join
- The FULL OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.

SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;

* Self Join
- A self join is a regular join, but the table is joined with itself.
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;

T1 and T2 are different table aliases for the same table.

SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER BY A.City;



