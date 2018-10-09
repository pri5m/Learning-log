# Introduction into database systems

## Definitions

**Database** An organised collection of digital data

**Database Mangagement system (DBMS)** A software application that facilitates definition, manipulation, maintenance and retrieval of data.

**Database system = Database DBMS**

**Data model** A collection of concepts for describing the structure of a database

**Conceptual model** Examples: Entity=Relationship diagram, UML class diagram

**Logical model** Still may be understood by end-users, more detail than conceptual models

**Physical model** Low level model

**Data schema** The description of data as specified during database design. Does not change very often

**Data Instance/state** Data in a db at a particular moment in time. Changes often.

## Users

- Database admins

- Database designers

- Software developers

- Business owners

- End users

## Data model

**Data Model** is a collection of concepts for describing the structure of a database.

Three types of data models:

**Conceptual model** – represents the Universe of Discourse at a high-level of abstraction, at a level
accessible to end-users and non-technical business experts. Specifies entities with a limited number of
attributes. Usually fits on one page. Contains relationships between entities, but omits cardinality and
nullability. It is independent of DBMS, data storage locations or technologies.
Examples: Entity-Relationship diagram, UML class diagram.

**Logical model** – still may be understood by end-users, it provides more details than a conceptual model,
but less than a physical model (e.g. it hides storage details). It will contain relationships between entities
that address cardinality and nullability. Data attributes will typically have datatypes with precisions and
lengths assigned. Also independent of technologies.

**Physical model** – a fully-attributed low-level data model that is dependent upon a specific technology
(DBMS) and data storage location. It includes objects such as views, primary key constraints, foreign key
constraints, indexes, security roles, stored procedures, etc.

 ## Three-Schema Architecture
 
**External Schema/View** - individual user's view of the DB (shows relevant data, while hiding the other). Each application has its own host language (e.g. Java, PHP) and may have DBMS language embedded within the host language.

**Conceptual Schema/View** - a single integrated definition of the data within an enterprise which is unbiased toward any single application of data and is independent of how the data is physically stored or accessed. A database administrator is responsible for the maintenance of the conceptual schema. A formal definition of the logical structure of the database, often represented as an Entity-Relationship diagram.

**Internal Schema/View** – represents the actual storage of a database and defines records, indexes, files and other physical attributes. For every conceptual table there may be several actual storage files. The schema for the external and internal levels is kept by the database in its Data Dictionary, also know as the **Catalogue** or **System Tables**.

## Data independence

**Logical data independence** A software application must not break when a change occurs in a conceptual schema (e.g. new attributes added).

**Physical data independence** – neither a software application(s) nor a conceptual schema must be affected by changes at the physical level (i.e. new indexes, new access paths) because physical data organisation and access methods are not parts of application logic and code.

+

**Functional independence** – change in implementation (method used to execute a certain function) must not affect software applications.

## Advantages of DB Design and DBSM

- Conceptual Modelling

- Data Independence (Logical and Physical)

- Functional Independence

- Managing Redundancy, Inconsistency and Conflicts

- Data Integrity

- Data Normalisation and De-normalisation

- Performance Improvement (efficient data processing)

- Backup and Recovery

- Security

## Classification of DBSM

➢By purpose (operational, analytical) 

➢By data model (flat file, network, hierarchical, relational, non-relational) 

➢By data organisation (row-oriented and column-oriented) 

➢By number of sites (centralised and distributed) 

➢Licensing (open source and commercial) 

➢Number of users (multiuser and single user)

## Types of db by purpose

Operational – collects, modifies and maintains data on a day-to-day basis in real-time. Deals with dynamic data that changes constantly as updates are made and always reflects up-to-date information.

Analytical – stores and tracks historical data, and time-dependent data.  Deals with static data which rarely changes, but new data may be added regularly. Typically read-only database.

## Types of db by data model

➢ Flat File Model (1960s) data stored in a single file (e.g. Excel file). Very good for small data, but has many disadvantages with large databases 

➢ Hierarchical Model (1970 - 1980s) data organised in a hierarchical tree-like structure where each child record has only one parent, but each parent record can have one or more child records (e.g. Windows Registry) 

➢ Network Model (1970 - 1980s) data are represented by collections of records, and relationships among data are represented by links, it allows each record to have multiple parent and child records, forming a generalized graph structure (e.g. CODASYL)

➢ Relational Model (1990s - )  the conceptual basis of relational databases. It was proposed by E.F. Codd in 1970, it is a method of structuring data using relations, which are grid-like mathematical structures consisting of columns and rows (e.g. tables). Since 1990s, it is the most popular data model around the world for data storage and processing. 

➢ Object-Oriented Model (1980s -1990s )  data is represented in the form of objects as used in objectoriented programming. In an object-oriented DBMS, the database model is integrated with the programming language,  while in relational DBMS there is a clearer division between the database model and the application. 

➢ NoSQL (non-relational) Models – (2000s-)  encompasses a broad range of different database technologies that were developed in response to the needs on modern (web)-applications which process large amount of structured, semi-structured, unstructured data and store them on clusters of distributed computers. There are different types of NoSQL databases: aggregateoriented (document, column family and key-value oriented) and graph model.

## Choices for DB and DBMS

❖ Platform support (Unix, Windows, Linux) 

❖ DBMS already in use 

❖ Vendor support 

❖ Architecture (client-server or shared file) 

❖ Possibility to implement in the cloud 

❖ Model Volatility 

❖Specific application needs

CW- Discussion and where you would implement it if you had a choice ( We had to do it in NoSQL)

# Relational Database Management Systems (RDBMS)

Main focus of the module

## Why and when to use

✓Dominated type of DBMS all over the world 

✓Adaptable to nearly every use-scenario 

✓Reliable 

✓There is an extensive existing body of knowledge/expertise about RDBMS 

✓An integration mechanism for many existing applications 

✓Effective for handling relationships, joins and complex transactions 

✓Ideal for structured data ✓Supports data validation (hence, ideal when a software application cannot handle validation and constraints)

Database = Schema The terms are used interchangeably

## DBMS 4 languages

**Data Manipulation Language (DML)** : Statements for managing data within schema objects.

•SELECT - Retrieve data from the a database 

•INSERT - Insert data into a table 

•UPDATE - Updates existing data within a table 

•DELETE - deletes all records from a table, the space for the records remain

**Data Control Language (DCL)**: Statements for granting/revoking access.

•GRANT - gives user's access privileges to database 

•REVOKE - withdraw access privileges given with the GRANT command

**Data Definition Language (DDL)** : Statements that define the database structure or schema.

•CREATE - to create objects in the database 

•ALTER - alters the structure of the database 

•DROP - delete objects from the database


**Transaction Control Lanugage (TCL)** : Statements for using transactions.

•BEGIN – Start a transaction. 

•COMMIT – Close a transaction and accept the results, 

•ROLLBACK – Rollback a transaction. 

•SAVE – Create a savepoint within a transaction

