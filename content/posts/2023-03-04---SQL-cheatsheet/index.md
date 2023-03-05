---
title: SQL Cheatsheet
date: "2023-03-04T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/SQL-cheatsheet"
category: "SQL"
tags:
  - "SQL"
  - "Cheatsheet"
  - "Conda"
description: "A list of most important SQL commands"
socialImage: "../../photo.jpg"
---



## Selecting Data: 

Grab all columns:
```
SELECT * 
FROM table_name;
```

Grab specific columns 
```
SELECT column1, column2, column3
FROM table_name
WHERE condition;
```


## Joining data

### Types of joins
- INNER JOIN returns only the rows where there is a match between the columns in both tables
- A LEFT JOIN returns all the rows from the left table and the matching rows from the right table
- A RIGHT JOIN returns all the rows from the right table and the matching rows from the left table


Outer joins add an additional layer of complexity. You can have a left or right outer join. 
An OUTER JOIN in SQL is used to return all the rows from one or both tables, including the non-matching rows

```
SELECT table_name_1.column_1, table_name_2.column_2
FROM table_name_1
INNER JOIN table_name_2
ON table_name_1.column_3 = table_name_2.column_3;
```


## Command options

```
SELECT - extracts data from a database
UPDATE - updates data in a database
DELETE - deletes data from a database
INSERT INTO - inserts new data into a database
CREATE TABLE - creates a new table
ALTER TABLE - modifies a table
DROP TABLE - deletes a table
CREATE INDEX - creates an index (search key)
DROP INDEX - deletes an index
```