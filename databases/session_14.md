# Big data

## Data warehouses

A data warehouse is a federated repository for all the data that an enterprise's various business systems collect. 
The repository may be physical or logical.

A data warehouse is a relational database that is designed for query and analysis rather than for transaction processing. It usually contains historical data derived from transaction data, but it can include data from other sources. It separates analysis workload from transaction workload and enables an organization to consolidate data from several sources.
In addition to a relational database, a data warehouse environment includes an extraction, transportation, transformation, and loading (ETL) solution, an online analytical processing (OLAP) engine, client analysis tools, and other applications that manage the process of gathering data and delivering it to business users.

There are two approaches to data warehousing, top down and bottom up. The top down approach spins off data marts for specific groups of users after the complete data warehouse has been created. The bottom up approach builds the data marts first and then combines them into a single, all-encompassing data warehouse.

### Characteristics

A common way of introducing data warehousing is to refer to the characteristics of a data warehouse as set forth by William Inmon:

**Subject Oriented** - Data warehouses are designed to analyse data (e.g. to analyse  company's sales data). Using this warehouse, you can answer questions like "Who was the best customer for this item last year?" This ability to define a data warehouse by subject matter, makes the data warehouse subject oriented.

**Integrated** - Integration is closely related to subject orientation. Data warehouses must put data from disparate sources into a consistent format. They must resolve such problems as naming conflicts and inconsistencies among units of measure. When they achieve this, they are said to be integrated.

**Non-volatile** – Non-volatile means that, once entered into the warehouse, data should not change. This is logical because the purpose of a warehouse is to enable you to analyse the past.

**Time Variant** - In order to discover trends in business, analysts need large amounts of data and must focus on change over time. This is very much in contrast to online transaction processing (OLTP) systems, where performance requirements demand that historical data be moved to an archive. 

## Online Analytical Processing (OLAP) Engine 

Online Analytical Processing (abbreviated OLAP) - a category of database processing oriented towards decision support. 
Typical applications of OLAP include business reporting for sales, marketing, management reporting, business process management (BPM), budgeting and forecasting, financial reporting etc.

OLAP tools enable users to analyze multidimensional data interactively from multiple perspectives. OLAP consists of three basic analytical operations: (1) consolidation (roll-up), (2) drill-down, and (3) slicing and dicing.

## Online Transaction Processing  (OLTP) Systems

OLTP systems facilitate and manage transaction-oriented applications, typically for data entry and retrieval transaction processing.

OLTP systems respond immediately to user requests.

OLTP systems process all kinds of queries (read, insert, update and delete), OLAP is generally optimized for read only and might not even support other kinds of queries.

OLTP systems gather input, process the data and update existing data to reflect the collected and processed information.

OLTP is typically contrasted to OLAP. OLTP is generally characterized by less complex queries and a larger volume, and oriented towards processing transactions rather than business intelligence or reporting. 

### Data Warehouses and OLTP requirements

**Workload** - Data warehouses are designed to accommodate ad hoc queries and data analysis. Data warehouse should be optimized to perform well for a wide variety of possible query and analytical operations. OLTP systems support only predefined operations. 

**Data modifications** - A data warehouse is updated on a regular basis by the ETL process (run nightly or weekly) using bulk data modification techniques. The end users of a data warehouse do not directly update the data warehouse except when using analytical tools, such as data mining, to make predictions with associated probabilities, assign customers to market segments, and develop customer profiles. In OLTP systems, end users routinely issue individual data modification statements to the database. The OLTP database is always up to date, and reflects the current state of each business transaction.

**Schema design** - Data warehouses often use denormalized or partially denormalized schemas to optimize query and analytical performance. OLTP systems often use fully normalized schemas to optimize update/insert/delete performance, and to guarantee data consistency.

**Typical operations** - A typical data warehouse query scans thousands or millions of rows. For example, "Find the total sales for all customers last month.“ A typical OLTP operation accesses only a handful of records. For example, "Retrieve the current order for this customer."

**Historical data** - Data warehouses usually store many months or years of data. This is to support historical analysis and reporting. OLTP systems usually store data from only a few weeks or months. The OLTP system stores only historical data as needed to successfully meet the requirements of the current transaction.

## Data Marts

A data mart is a repository of data that is designed to serve a particular community of knowledge workers.
Data warehousing emphasizes the capture of data from diverse sources for useful analysis and access, but does not generally start from the point-of-view of the end user who may need access to specialized, sometimes local databases. The latter idea is known as the data mart.

A data warehouse is a central repository for all an organization's data. The goal of a data mart is to meet the particular demands of a specific group of users within the organisation, such as human resource management. Generally, an organization's data marts are subsets of the organisation's data warehouse.

Because data marts are optimized to look at data in a unique way, the design process tends to start with an analysis of user needs. In contrast, a data warehouse's design process tends to start with an analysis of what data already exists and how it can be collected and managed in such a way that it can be used later on. A data warehouse tends to be a strategic, but somewhat unfinished concept; a data mart tends to be tactical and aimed at meeting an immediate need.

## Distributed systems

A distributed system consists of a collection of autonomous computers, connected through a network and distribution middleware, which enables computers to coordinate their activities and to share the resources of the system, so that users perceive the system as a single, integrated computing facility.

Characteristics:

- Multiple autonomous components 

- Components are not shared by all users 

- Resources may not be accessible 

- Software runs in concurrent processes on different processors 

- Multiple Points of control 

- Multiple Points of failure


- Data stored at a number of sites, each site logically consists of a single processor. 

- Processors at different sites are interconnected by a computer network, no multiprocessors 

- Distributed database is a database, not a collection of files, i.e. data logically related as exhibited in the users’ access patterns 

- Distributed -DBMS is a full-fledged DBMS, not a remote file system

- Resource Sharing 

- Openness 

- Concurrency 

- Scalability 

# NoSQL Databases (beyond relational model)

[Intro to NoSQL by Martin Fowler](https://www.youtube.com/watch?v=qI_g07C_Q5I)

### Characteristics

➢Non-relational, Not-Only-SQL

➢Cluster-friendly (although, not for all of them this is the primary focus)

➢Open-source (predominantly, but not always)

➢Schema-less (not quite)

All NoSQL databases claim to be schema-less, which means there is no schema enforced by the database themselves, but
there is the implicit schema in any code that accesses the data.

➢Flexible (add any node without a schema)

### NoSQL data model four types

1. Key Values Store – aggregate-oriented

2. Document - aggregate-oriented

3. Column family - aggregate-oriented

4. Graph model – decomposes data even more than Relational

ALL these four types are said to be schema-less

Aggregate-oriented - databases are designed for storing and running data on clusters. You do
not do transactions outside aggregate. 

### When to use

1. You have big data – large amount data, more than you could fit in one DB on one machine.
Running RDB on clusters is a large-scale data problem

2. Data model does not fit well with business model (articles in journalism, pushing the article
in and out is easier than splitting metadata in RDB)

3. You need to get rid of impedance mismatch problem

4. You are aiming for easier development and looking for the improvement of programmer
productivity by using a database that better matches application's needs

5. The project involves dealing with analytics – data warehousing, information mining

6. You need to improve data access performance via a combination of handling larger data
volumes, reducing latency, and improving throughput.

## Disadvantages

➢Immature

➢Lack of experience (not like with RDBMSs)

➢It involves taking a risk (Is it a strategic problem for your business?)

➢If it is a standard project, utility – go with something you know

➢Better throughput and concurrency, at the expense of stability, consistency, or availability.

The choice to use a NoSQL database is often based on hype, or
a wrong assumption that relational databases cannot perform as
well as a NoSQL database. Operational costs, as well as other
stability and maturity concerns, are often overlooked by
engineers when it comes to selecting a database. Yoav Abrahami

### Using MySQL as a NoSQL engine

Design your schema to be optimized for reads:

Do not normalize.

Fields only exist to be indexed. If a field is not needed for an index, store it in one blob/text field (such as JSON
or XML).

Do not use foreign keys.

Design your schema to enable reading a single row on query.

Any field that is not used as a condition in a query has been folded into a single blob field

Do not perform table alter commands. Table alter commands introduce locks and downtimes. Instead, use live
migrations.

When querying data:

Query for records by primary key or by index.

Avoid using DB locks or complex queries

Do not use joins.

Do not use aggregations.

Run housekeeping queries (BI, data exploration, etc.) on a replica, not on the master database.

# JSON objects

JSON Syntax Rules

➢JSON syntax is derived from JavaScript object notation syntax:

➢Data is in name/value pairs

➢Data is separated by commas

➢Curly braces hold objects

➢Square brackets hold arrays

```
{"employees":[
{ "firstName":"John", "lastName":"Doe" },
{ "firstName":"Anna", "lastName":"Smith" },
{ "firstName":"Peter", "lastName":"Jones" }
]}

```

### The JSON Data Type in MySQL

MySQL's addition of a JSON data type makes the relational database easier to use and blurs the lines
between SQL and NoSQL databases.

Before MySQL 5.7, you could store a JSON-formatted document in a character field. But large strings are
messy to search, and writing regular expressions for finding values within that string can be a frustrating
experience. And if you changed one part of the string you had to rewrite the entire string, which is terribly
inefficient but was necessary up to MySQL 5.6.

MySQL introduced a native JSON data type in MySQL 5.7. So like an integer, a char, or a real, there became
a way to store an entire JSON document in a column in a table of a database—and this document in a
column could be roughly a gigabyte in size! The server would make sure it was a valid JSON document and
then save it in a binary format that's optimized for searching.

The data type also comes with over 20 functions. These functions will extract key-value pairs from the
document, update data, provide metadata about the data, output non-JSON columns in JSON format, and
more.

### Advantages

The JSON data type provides these advantages over storing JSON-format strings in a string column:

•Automatic validation of JSON documents stored in JSON columns. Invalid documents produce an error.

•Optimized storage format. JSON documents stored in JSON columns are converted to an internal format that permits
quick read access to document elements. When the server later must read a JSON value stored in this binary format, the
value need not be parsed from a text representation. The binary format is structured to enable the server to look up subobjects
or nested values directly by key or array index without reading all values before or after them in the document.


[Operations docs](https://dev.mysql.com/doc/refman/5.7/en/json-function-reference.html)
