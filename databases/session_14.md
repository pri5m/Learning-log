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


