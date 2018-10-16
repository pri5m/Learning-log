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

## LEFT JOIN: 

Return all rows from the left table, and the matched rows from the right table

LEFT JOIN returns all rows from the left table (table1), with the matching rows in the right table
(table2). The result is NULL in the right side when there is no match.

```
SELECT column_name(s)
FROM table1
LEFT OUTER JOIN table2
ON table1.column_name=table2.column_name;
```

## RIGHT JOIN: 

Return all rows from the right table, and the matched rows from the left table

RIGHT JOIN returns all rows from the right table (table2), with the matching rows in the left
table (table1). The result is NULL in the left side when there is no match.

```
SELECT column_name(s)
FROM table1
RIGHT OUTER JOIN table2
ON table1.column_name=table2.column_name;
```

## FULL OUTER JOIN: 

Return all rows when there is a match in ONE of the tables

FULL OUTER JOIN returns all rows from the left table (table1) and from the right table (table2),
i.e. it combines the results of LEFT and RIGHT joins. All rows from both tables will be included in
the result grid irrespectively whether there is a matching row in another table.

```
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name=table2.column_name;
```

## Cross join

CROSS JOIN produces a result
set which is the product of
rows of two associated tables.
This is called a Cartesian
Product.

```
SELECT size, color
FROM sizes
CROSS JOIN colors
```

