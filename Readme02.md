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

**Query order of execution**
1. FROM and JOINs <br/>
The FROM clause, and subsequent JOINs are first executed to determine the total working set of data that is being queried. This includes subqueries in this clause, and can cause temporary tables to be created under the hood containing all the columns and rows of the tables being joined.<br/>

2. WHERE <br/>
Once we have the total working set of data, the first-pass WHERE constraints are applied to the individual rows, and rows that do not satisfy the constraint are discarded. Each of the constraints can only access columns directly from the tables requested in the FROM clause. Aliases in the SELECT part of the query are not accessible in most databases since they may include expressions dependent on parts of the query that have not yet executed.<br/>


3. GROUP BY <br/>
The remaining rows after the WHERE constraints are applied are then grouped based on common values in the column specified in the GROUP BY clause. As a result of the grouping, there will only be as many rows as there are unique values in that column. Implicitly, this means that you should only need to use this when you have aggregate functions in your query. <br/>

4. HAVING <br/>
If the query has a GROUP BY clause, then the constraints in the HAVING clause are then applied to the grouped rows, discard the grouped rows that don't satisfy the constraint. Like the WHERE clause, aliases are also not accessible from this step in most databases. <br/>


**examble**

```
SELECT director, SUM(domestic_sales + international_sales) as Cumulative_sales_from_all_movies
FROM movies
    INNER JOIN boxoffice
        ON movies.id = boxoffice.movie_id
GROUP BY director;
```
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155299126-2148d6da-6741-4f97-8549-3ee0db47ca7e.png)
---------------------------------------------------------------------------------------------------------------------------

### SQL Lesson 13: Inserting rows
when we want to insert data to row in tables we use the INSERT keyword .

**Insert statement with values for all columns**

```
INSERT INTO mytable
VALUES (value_or_expr, another_value_or_expr, …),
       (value_or_expr_2, another_value_or_expr_2, …),
       …;
```

**examble**

``
INSERT INTO movies VALUES (4, "Toy Story 4", "El Directore", 2015, 90);
``
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155299664-31e75ffb-b31b-491d-857d-257db0d2f9df.png)
----------------------------------------------------------------------------------------------------------------------

### SQL Lesson 14: Updating rows

when we want to update data from table we use the schema update .

**Update statement with values**
``
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;
``

**examble**
``
UPDATE movies
SET director = "John Lasseter"
WHERE id = 2;

``

**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155300071-8888d703-61f5-4cf8-b87b-9d8c8fbd75e7.png)

----------------------------------------------------------------------------------

### SQL Lesson 15: Deleting rows
when we want to delete data  we use the delete schema .


**Delete statement with condition**

``
DELETE FROM mytable
WHERE condition;

``

**examble**
``
DELETE FROM movies
where year < 2005;
``

``
DELETE FROM movies
where director = "Andrew Stanton";
``
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155301138-ac61cba9-6856-4200-a3e7-44bb7aa27ee0.png)

---------------------------------------------------------------------------------------------------------------------------

### SQL Lesson 16: Creating tables

when we want to create table we use create table schema as folows:

```
Create table statement w/ optional table constraint and default value
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);

```
**Noth**
we must select the data types of column as the table belwo:
![image](https://user-images.githubusercontent.com/97642724/155301642-2d65433a-9df6-4afc-9d75-6137fb7d2628.png)

**Table constraints**
We aren't going to dive too deep into table constraints in this lesson, but each column can have additional table constraints on it which limit what values can be inserted into that column. This is not a comprehensive list, but will show a few common constraints that you might find useful.

![image](https://user-images.githubusercontent.com/97642724/155301773-dfb1abab-b8a5-4024-8bd3-8ccabb73b525.png)


**examble**

```
CREATE TABLE movies (
    id INTEGER PRIMARY KEY,
    title TEXT,
    director TEXT,
    year INTEGER, 
    length_minutes INTEGER
);

```
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155301954-138463b5-627f-45ef-8a10-f1c05cccf3d8.png)

----------------------------------------------------------------------------------------------

### SQL Lesson 17: Altering tables

when we want to adding column  to table we use the adding column schema .

**Altering table to add new column(s)**

``
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint 
    DEFAULT default_value;
    
``

**Removing columns**

``
ALTER TABLE mytable
DROP column_to_be_deleted;

``

**Renaming the table**

``
ALTER TABLE mytable
RENAME TO new_table_name;

``
**examble**
``
ALTER TABLE Movies
  ADD COLUMN Aspect_ratio FLOAT DEFAULT 2.39;
  
``
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155302560-775367f8-7b30-4206-8353-dfe32f056b48.png)

-----------------------------------------------------------------------

### SQL Lesson 18: Dropping tables

if we want to delete table we use the drop keyword as this statement.

**Drop table statement**

``
DROP TABLE IF EXISTS mytable;

``

**examble**

`
DROP TABLE Movies;
`
**Leson Image**
![image](https://user-images.githubusercontent.com/97642724/155303056-a9af84e5-d64b-4373-825f-cf6564407831.png)

-----------------------------------------------------------
![image](https://user-images.githubusercontent.com/97642724/155303175-ee169ee3-6738-4e3d-80c2-e98d6cb78b57.png)

---------------------------------------------------------------------------------------------------------


[All Leson resores it taken from =>](https://sqlbolt.com/)










 
