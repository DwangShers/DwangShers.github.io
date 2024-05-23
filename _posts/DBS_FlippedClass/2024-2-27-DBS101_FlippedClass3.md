---
Title: DBS101 Flipped Class 3
categories: [DBS101, Flipped_Class3]
tags: [DBS101]
---

## Topic : Null Values and Set Operations in SQL
----

In our third flipped class, the Expert Group Strategy was used. For the flipped class 1 hour and 30 minutes was provided, whereby 30 minutes for reading time, 30 minutes for discussion time, and 30 minutes for presenting to our home group. 
The Null values in SQL and Set operations in SQL were the topics, so we were divided into 4 groups and for each topics there were 2 groups. 
For my expert group we got the topic Null Values in SQL. 

---
The  expected outcomes from this flipped class were know the difference between types of database users, understand the roles and funcitons of database administrators.
For this flipped class, our tutor provided us resources for more information.

Website links:

"https://www.javatpoint.com/dbms-sql-set-operation"

"https://www.w3schools.com/sql/sql_null_values.asp"

"https://www.geeksforgeeks.org/sql-null-values/"

"https://www.javatpoint.com/set-operators-in-sql"

From Textbook,ebook.(Database systems fundamentals, Unit 3, page 84-89)

---
For my expert groups we got the topic SQL Set Operation. In simple SQL set operation is used to combine the two or more SQL SELECT statements.

### SQL Set Operation

Types of Set Operation:

1. Union
2. UnionAll
3. Intersect
4. Minus

#### Union
The union operation is used to combine two sets into one without any duplicates or repeated items.
 
For Example:

First table

![alt text](/image/union1.png)

Second table

![alt text](/image/union2.png)

{SELECT * FROM First UNION SELECT * FROM Second;}

Result set table:

![alt text](/image/unionResult.png)


#### UnionAll
Union All operation is equal to the Union operation but it returns the set without removing duplicates.

{SELECT * FROM First UNION ALL SELECT * FROM Second;}

Result set table:

![alt text](/image/unionAll.png)

#### Intersect
Intersect operation is used to find the common elements between two sets. 

{SELECT * FROM First INTERSECT SELECT * FROM Second;}

Result set table:

![alt text](/image/intersect.png)

#### Minus 
Minus operation is used to display the rows which are present in the first query but absent in second query.

{SELECT * FROM First MINUS SELECT * FROM Second;}

Result set table:

![alt text](/image/minus.png)

---
When I went back to my home group, I taught about set operations to my home members and they also taught me about the Null Values in SQL.

### Null Values in SQL

The term Null value represents a missing or unknown value in a database table. 

SQL automatically inserts NULL when no specific value is provided for a field.

#### Importance of a Null Value
* It is important to understand that a NULL value differs from a zero value.
* A NULL value is used to represent a missing value, but it usually has one of three different interpretations: 
  1. The value unknown (value exists but is not known)
  2. Value not available (exists but is purposely withheld)
  3. Attribute not applicable (undefined for this tuple)
* It is often not possible to determine which of the meanings is intended. Hence, SQL does not distinguish between the different meanings of NULL.

#### Principles of NULL values
* Setting a NULL value is appropriate when the actual value is unknown, or when a value is not meaningful.
* A NULL value is not equivalent to a value of ZERO if the data type is a number and is not equivalent to spaces if the data type is a character.
* A NULL value can be inserted into columns of any data type.
* A NULL value will evaluate NULL in any expression.
* Suppose if any column has a NULL value, then UNIQUE, FOREIGN key, and CHECK constraints will ignore by SQL.