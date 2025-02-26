can perform on neon.tech ,avion.io
# # Types of DATABASE

###### NOSQL DATABASE 

store database data in schema less fashion,
extremely lean and fast way to store data 
*MONGODB*

###### Graph Database
data stored in a form of graph 
*NEO4J*

###### Vector Database
data stored in a form of vector ,useful for AI applications 
*PINCONE*

###### SQL Database
data stored in a form of tables and rows
most full stack use sql database
*mysql , postgres*


### why not NO SQL
its schema-less, app  can be corrupt when it grows


it can lead runtime errors inconsistent database, is to flexible for an app that need strictness


### why SQL
Define your schema,
Put in data that follows schema
update the schema as your app changes or grows


4 parts when using sql 
connect the database
using library lets you connect and put the data 
creating a table  and define schemas
run queries on the database


### using library that lets you connect nd put data in it
**psql**  for postgress application 
**pg** for node application 


### creating a table and defining its schema
a single database can have multiple tables

*SQL=structured query language* 

SERIAL is a auto increment datatype ,every time row inserted it increases by one automatically



### Relationships and Transactions
in nosql you can store data of any shape 
but in sql you have to store data according to schema 





## joins
**Types of Joins**

1. **INNER JOIN**

Returns rows that have matching values in both tables.

**Syntax**:
```
SELECT a.*, n.*

FROM address AS a

INNER JOIN nusers AS n

ON a.userid = n.id;
```


2. **LEFT JOIN (or LEFT OUTER JOIN)**

Returns all rows from the left table, and the matching rows from the right table. If there’s no match, NULLs are returned for columns from the right table.

**Syntax**:

```
SELECT n.*, a.city, a.country
FROM nusers AS n
LEFT JOIN address AS a
ON n.id = a.userid;

```
3. **RIGHT JOIN (or RIGHT OUTER JOIN)**

Returns all rows from the right table, and the matching rows from the left table. If there’s no match, NULLs are returned for columns from the left table.

**Syntax**:
```
SELECT a.*, n.username, n.email
FROM address AS a
RIGHT JOIN nusers AS n
ON a.userid = n.id;
```

4. **FULL JOIN (or FULL OUTER JOIN)**

Returns rows when there is a match in either table. If there’s no match, NULLs are returned for columns of the missing table.

**Syntax**:
```
SELECT n.*, a.*
FROM nusers AS n
FULL JOIN address AS a
ON n.id = a.userid;
```

5. **CROSS JOIN**

Produces the Cartesian product of the two tables, meaning every row in the first table is paired with every row in the second table.

**Syntax**:
```
SELECT n.username, a.city
FROM nusers AS n
CROSS JOIN address AS a;
```
• **INNER JOIN**: When you need only matching rows.

• **LEFT JOIN**: When you want all rows from the left table, even if there’s no match in the right table.

• **RIGHT JOIN**: When you want all rows from the right table, even if there’s no match in the left table.

• **FULL JOIN**: When you need all rows from both tables.

• **CROSS JOIN**: When you want every possible combination of rows.