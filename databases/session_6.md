# Joins

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766720-dt-content-rid-11793832_2/courses/1819-CM6211/Week%203%20-%20Session%206%20-%20%20More%20SQL%20%28JOINS%20CASE%29.pdf)

## INNER JOIN: 

Returns all rows when there is at least one match in BOTH tables.

INNER JOIN (or JOIN) combines rows from two or more tables, based on a common field
between them. There MUST be that common field in both tables for a row to be included in the
result grid.

```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name=table2.column_name;
```

## LEFT OUTER JOIN: 

Return all rows from the left table, and the matched rows from the right table

## RIGHT OUTER JOIN: 

Return all rows from the right table, and the matched rows from the left table

## FULL OUTER JOIN: 

Return all rows when there is a match in ONE of the tables

