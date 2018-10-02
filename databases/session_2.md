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

-Entity

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

