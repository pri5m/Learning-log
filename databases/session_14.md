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

