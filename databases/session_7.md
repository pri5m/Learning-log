# Views

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766721-dt-content-rid-11931974_2/courses/1819-CM6211/Week%203%20-%20Session%207%20%20-%20%20Even%20More%20SQL%20-%20Views%20Truncate%20and%20Exists%281%29.pdf)

A database view is a virtual table or logical table which is defined as a SQL SELECT query with joins. You can query a view.

### Advanatges

➢Simplify complex queries

➢Limit data access to specific users

➢Provide extra security layer

➢Enable computed columns

➢Enable backward compatibility (legacy)

### Disadvantages

➢Performance: querying data from a database view can be slow, especially, if the view is created
based on other views.

➢Table dependency: you create a view based on some actual underlying tables within a
database. Whenever you change the structure of those tables that view is associated with, you
have to change the view as well.

➢You cannot create an index on a view.

# Materialised views

A Materialized View (MV) is the pre-calculated (materialized) result of a query. The result of a
Materialized View is stored in the schema.

Materialized Views are used when quick response is required, while the query to build the view
would take long time to be executed.

Materialized views are useful when the system performs large number of queries on the view
while the original data changes not so frequently or high precision of information is not critical.

Materialized Views have to be refreshed at a frequency which will depend on business
requirements.

MySQL does doesn't support materialized views, but it is possible simulate materialized views

### Pros and cons

➢Materialised Views can help to speed up queries which rely heavily on aggregated results.

➢It may help to decrease read load on the system.

➢You need good knowledge of SQL and Procedural SQL to implement materialised views.

➢You would typically use it only when you process large volumes of data.

[Wiki page on materialised views](https://en.wikipedia.org/wiki/Materialized_view)
