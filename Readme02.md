## Introduction to SQL
### SQL Lesson 1: SELECT queries 101
-------------------------------------

in this Leson we use the select keyword to get or  retrieve data from a SQL database , the SQL refer to Structured Query Language , the query 
just a statement which declares what data we are looking for , the select keyword stacture As follows : 

```

SELECT columnName, another_columnName, …
FROM tableName;
```

**Some Exambel**
---------------------------
To select all data from the table :
````
SELECT * FROM tableName;
````
To select some data such as age form pepole table :
```
SELECT age FROM pepole;
```
**Leson image**

![leson 1](https://user-images.githubusercontent.com/97642724/155285195-7d47e9ac-29fe-4c01-b696-194a0855dffd.JPG)

### SQL Lesson 2: Queries with constraints (Pt. 1) 
---------------------------------------------------------
When we want to select some data with specific columns and information we use the **WHERE**  keyword to select data with some condition .

Select query with constraints

```
SELECT columnName, another_columnName, …
FROM tableName
WHERE condition
```
**Some Exambel** <br/>
to select movies it have the id =6
```
SELECT id, title FROM movies 
WHERE id = 6;
```
to select movies product between 2000 and 2010 <br/>

`````

SELECT title, year FROM movies
WHERE year BETWEEN 2000 AND 2010;

``````

**Leson image**
![leson 2](https://user-images.githubusercontent.com/97642724/155286543-22de1079-66f3-4505-b062-9da4ffe1c499.JPG)


### SQL Lesson 3: Queries with constraints (Pt. 2)
-----------------------------------------------------
When writing WHERE clauses with columns containing text data, SQL supports a number of useful operators to do things like case-insensitive string comparison and wildcard pattern matching. We show a few common text-data specific operators below:
![image](https://user-images.githubusercontent.com/97642724/155287496-09d6d695-33ae-4e5c-805d-013ac9bb4a7e.png)


**Select query with constraints**

````
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
    
 ````
 
 **examble**
 
 ```
 SELECT title, director FROM movies 
WHERE title LIKE "Toy Story%";

```
 
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155287935-acc2e2b5-0fc7-4fdd-bd7f-bf6c85b6a349.png)

----------------------------------------------------------------

### SQL Lesson 4: Filtering and sorting Query results :

when we want to get some data from table such as person who has age 36 , but some time many person has the same age thath caused duplicate data 
so we use the **DISTINCT** keyword to discard rows that have a duplicate column value.

**Select query with unique results**

```
SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);

```

**Ordering results**
to order the data ascending or descendig we use the ORDER BY keyword.


**Select query with ordered results**

```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```
**LIMIT KEYWORD**
The LIMIT will reduce the number of rows to return.

**Select query with limited rows**


````
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;

````


**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155289065-3e1b0d4d-b23d-4551-a882-b3b47bdcd30a.png)
-------------------------------------------------------------------------------------------------------------------------

### SQL Lesson 6: Multi-table queries with JOINs

Up to now, we've been working with a single table, but entity data in the real world is often broken down into pieces and stored across multiple orthogonal tables using a process known as normalization

**Database normalization**
THE  Database normalization THE MOST USEFFUL WAY  because it reduce duplicate  data in any single table.

**Multi-table queries with JOINs**
when we want to select data from more then table we use the JION keyword alson to connect the tables ech ether we need to primary key.


**Select query with INNER JOIN on multiple tables**

`````
SELECT column, another_table_column, …
FROM mytable
INNER JOIN another_table 
    ON mytable.id = another_table.id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;

`````


**Examble**

````
SELECT title, domestic_sales, international_sales 
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;
    
````

**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155290286-a5ac0df0-e652-4672-ba04-385a793a4564.png)


-------------------------------------------------------------------------

### SQL Lesson 7: OUTER JOINs
Depending on how you want to analyze the data, the INNER JOIN we used last lesson might not be sufficient because the resulting table only contains data that belongs in both of the tables.

If the two tables have asymmetric data, which can easily happen when data is entered in different stages, then we would have to use a LEFT JOIN, RIGHT JOIN or FULL JOIN instead to ensure that the data you need is not left out of the results.

**Select query with LEFT/RIGHT/FULL JOINs on multiple tables**

````
Select query with LEFT/RIGHT/FULL JOINs on multiple tables
SELECT column, another_column, …
FROM mytable
INNER/LEFT/RIGHT/FULL JOIN another_table 
    ON mytable.id = another_table.matching_id
WHERE condition(s)
ORDER BY column, … ASC/DESC
LIMIT num_limit OFFSET num_offset;

````

**examble**

```
SELECT DISTINCT building FROM employees;

```
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155293131-234279e8-9d35-4068-b070-89082c42ca29.png)

--------------------------------------------------------------------------------------------------------------


### SQL Lesson 8: A short note on NULLs

if i have store of computer and i write the information for each costmures in my site , if some coustomes not want the receipt , then i put the column on receipt is empty , the empty is the defult value
if the devloper not assghin in dataBase to defult value then the value of the receipt is null .
 we use the IS NULL or IS NOT NULL KEYWORD   TO find the data it have the null value.
 
 **Select query with constraints on NULL values**
 
 ````

SELECT column, another_column, …
FROM mytable
WHERE column IS/IS NOT NULL
AND/OR another_condition
AND/OR …;

````

**examble**

```
SELECT name, role FROM employees
WHERE building IS NULL;

```

**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155294712-520fea1b-ed4c-4ac1-91b0-1bf64c80f170.png)
------------------------------------------------------------------------

### SQL Lesson 9: Queries with expressions

In addition to querying and referencing raw column data with SQL, you can also use expressions to write more complex logic on column values in a query. These expressions can use mathematical and string functions along with basic arithmetic to transform values when the query is executed, as shown in this physics example.

````
SELECT particle_speed / 2.0 AS half_particle_speed
FROM physics_data
WHERE ABS(particle_position) * 10.0 > 500;
````

The use of expressions can save time and extra post-processing of the result data, but can also make the query harder to read, so we recommend that when expressions are used in the SELECT part of the query, that they are also given a descriptive alias using the AS keyword.


**Select query with expression aliases**

``
SELECT col_expression AS expr_description, …
FROM mytable;
``


**examble**

```
SELECT title, (domestic_sales + international_sales) / 1000000 AS gross_sales_millions
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;
    
```
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155296145-dbfa79c7-8cdf-44e6-a1b7-629bcf7d69e3.png)

------------------------------------------------------------------------------

### SQL Lesson 10: Queries with aggregates (Pt. 1)

In addition to the simple expressions that we introduced last lesson, SQL also supports the use of aggregate expressions (or functions) that allow you to summarize information about a group of rows of data

**Select query with aggregate functions over all rows**

```
SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …
FROM mytable
WHERE constraint_expression;

```

**Common aggregate functions**
![image](https://user-images.githubusercontent.com/97642724/155296681-29d478ed-5353-4695-86eb-cc213bdba20e.png)


**Select query with aggregate functions over groups**

````
SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …
FROM mytable
WHERE constraint_expression
GROUP BY column;
````

**examble**

``
SELECT role, AVG(years_employed) as Average_years_employed
FROM employees
GROUP BY role;
``

**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155297119-5c8a36fb-e007-49c4-a961-f23365d1a6e2.png)

---------------------------------------------------------------------------------------------------

### SQL Lesson 11: Queries with aggregates (Pt. 2)
SQL allows us to do this by adding an additional HAVING clause which is used specifically with the GROUP BY clause to allow us to filter grouped rows from the result set.

**Select query with HAVING constraint**
```
SELECT group_by_column, AGG_FUNC(column_expression) AS aggregate_result_alias, …
FROM mytable
WHERE condition
GROUP BY column
HAVING group_condition;
```

examble

``
SELECT role, COUNT(*)
FROM employees
GROUP BY role;
``
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155298079-6af903bc-e83f-48c3-9444-a7e4424a1bdb.png)
-----------------------------------------------------------------

### SQL Lesson 12: Order of execution of a Query

Now that we have an idea of all the parts of a query, we can now talk about how they all fit together in the context of a complete query.

````
SELECT DISTINCT column, AGG_FUNC(column_or_expression), …
FROM mytable
    JOIN another_table
      ON mytable.column = another_table.column
    WHERE constraint_expression
    GROUP BY column
    HAVING constraint_expression
    ORDER BY column ASC/DESC
    LIMIT count OFFSET COUNT;
    
````




 
