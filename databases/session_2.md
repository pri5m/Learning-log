# Relational model

➢Data is stored in tables (relations) 

➢Each relation consists of rows and columns 

➢Each relation must have a unique name, a header and body (the header = schema, the body  = instance) 

➢The header is the list of columns in the relation 

➢A relation may contain an identifying column(s) (primary key) 

➢Keys are used for unique row identification and for establishing relationships between tables 

➢A set of rules (integrity constraints) enforces data integrity 

➢Data normalisation ensures effective data storage and processing

## Key concepts

- Relation (Table)

- Entity

- Tuple (Row or Record)

- Attribute (Column or Field) 

- Domain (Pool of legal values) 

- Degree Primary Key (Unique Identifier) 

- Foreign Key 

- Composite Key 

- Candidate Key 

- Relationship


**Table (Relation)** – represents a particular singular Entity (a subject) of the Universe of Discourse. An Entity is something of importance that must be represented in a database (People, Business Concepts, Objects).

**Column (Attribute)** – represents a characteristic of the Entity.

**Row (Record, Tuple)** – a unique instance of the Entity in the table. Each value in the row belongs to a specific domain.

**Degree** - the number of domains in a relation (the number of columns in a table)

## Domain

Domain – a named set of allowed values (data type is a domain).

Domains could be used to impose semantic constraints (e.g. in a conditional clause it prevents comparison of values from different domains)

## Properties of a relation

NOT EVERY TABLE is a RELATION

RELATION is a two-dimensional table that has the following characteristics: ➢Each column within a relation must have a unique name

➢Rows in a relation are unordered (order has no meaning) 

➢Columns in a relation are unordered (order has no meaning) 

➢Cells in a relation contain only single values (i.e. arrays of values are not allowed) 

➢All values in the same columns must be of the same data type (domains) 

➢There are no identical rows in the relation

## Primary key

An attribute or a minimum set of attributes that uniquely identifies a row within a relation.

Use a field as a primary key only if:

➢The field uniquely identifies the row 

➢The field contains unique values 

➢The field does not contain unknown values 

➢The values of the field cannot be optional 

➢The value of the field cannot be modified

## Candidate key

A candidate key is a minimal set of attributes necessary to identify a row (a minimal superkey).

A candidate Key has a potential to become a Primary Key, but it was not chosen to become the Primary Key.

A primary Key is a candidate key, which was chosen to become a primary key.

A simple key is the key that consists of a single column (attribute).

## Composite key

A key that is composed of two or more columns (attributes).


## Surrogate key

➢Surrogate key is a unique, numeric value 

➢It is added to the row to serve as a primary key 

➢It has no meaning in the context of the Entity represented by the relation 

➢It is often used to replace a composite key 

➢It is typically hidden in front-end applications

## InnoDB

We will be using this engine

➢To maintain data integrity, InnoDB supports FOREIGN KEY constraints. With foreign keys, inserts, updates, and deletes are checked to ensure they do not result in inconsistencies across different tables. 

## Foreign key

The relationships between the tables are modelled by assigning Foreign Keys.

Foreign Key is a primary key from one table which is embedded into another table in order to indicate a relationship between the instances of the Entities from these two tables.

The key is called a Foreign Key in a table which receives it and it is called a Primary Key in the table it originates from.

## Data integrity

**Data integrity** – is ensured by integrity rules which may be semantical and syntactical. Integrity rules may be stored in a DBMS or implemented at the application level. 

Semantical rules address the issues with the meaning of concepts (e.g. ID is not unique), while syntactical rules address the issues with the representation form (e.g. a date is a DATE, rather than a STRING).

## Integrity constraints

To ensure data integrity relational model introduces a number of constraints.

The major types of integrity constraint are:

❖ Domain constraint 

❖ Entity integrity constraint 

❖ Referential integrity constraint

## Domain constraint

A domain is the set of all unique values permitted for an attribute. 

E.g. a domain of day-of-week is Monday, Tuesday ... Sunday.

This in effect is defining rules for a particular attribute. If it is determined that an attribute is a date then it should be implemented in the database to prevent invalid dates being entered.

A classic example:

The data from a legacy system is loaded into a newly designed database. In the new system, column that holds dates has data type ‘DATE’. In the old system, the dates were held as character strings (1 May 2016). During the data migration, the dates from the old system are rejected by the new system as invalid values.

## Entity integrity

This is a basic constraint in the relational model.

➢ Every relation must have a primary key. 

➢ The primary key for a row is unique (it does not match the value of any other row in the table) 

➢ The primary key is not NULL, no component of the primary key may be set to NULL.

An RDBMS enforces Entity Integrity by not allowing operations such as INSERT and UPDATE to produce an invalid primary key. Any operation that creates a duplicate primary key or one containing NULL is rejected.

## Referential integrity

All values of a given foreign key must match values of the corresponding primary key (or be Null)

```
Lecturers (PK_lecturerID, lecturerName, lecturerSurname) 
Modules (PK_moduleCode,  moduleTitle,  FK_lecturerID)
```

Every value appearing in the FK_lecturerID column of table Modules must either be a NULL or a value that matches a value appearing in the PK_lecturerID column of table Modules. Modules is the referencing relation (child) and Lecturers is the referenced relation (parent).

*When a row in a table references a corresponding record in another table, the corresponding record MUST exist!*

## Referential integrity enforcement

RDBMSs enforce referential integrity in order to preserve the integrity of data.

Statements  INSERT and UPDATE CANNOT create a non-null foreign key unless a corresponding primary key exists.

Any operation that produces a non-null foreign key value without a matching primary key value is REJECTED. 

Statements  INSERT and DELETE CANNOT remove or change a primary key while a referencing foreign keys exist.

**In MySQL**

When an UPDATE or DELETE operation affects a key value in the parent table that has matching rows in the child table, the result depends on the referential action specified using ON UPDATE and ON DELETE subclauses of the FOREIGN KEY clause. 

```
[CONSTRAINT [symbol]] 
FOREIGN KEY [index_name] (index_col_name, ...) 
REFERENCES tbl_name (index_col_name,...) 
[ON DELETE reference_option] 
[ON UPDATE reference_option] 

reference_option: RESTRICT | CASCADE | SET NULL | NO ACTION
```

MySQL InnoDB supports four options: 

➢ **CASCADE**: Delete or update the row from the parent table, and automatically delete or update the matching rows in the child table. Both ON DELETE CASCADE and ON UPDATE CASCADE are supported. 

➢ **SET NULL**: Delete or update the row from the parent table, and set the foreign key column or columns in the child table to NULL. 

➢ **RESTRICT**: Rejects the delete or update operation for the parent table. Specifying RESTRICT (or NO ACTION) is the same as omitting the ON DELETE or ON UPDATE clause. 

➢ **NO ACTION**: A keyword from standard SQL. In MySQL, equivalent to RESTRICT. The MySQL Server rejects the delete or update operation for the parent table if there is a related foreign key value in the referenced table. 

# Homework

When launching a downloaded sql file in the workspace, you auto create a connection to the MySQL DBMS. A connection to the DBMS is also made when using command line SQL. There is no 'off' and 'on'. The only limitation is how many connections can be supported at any one given time.
