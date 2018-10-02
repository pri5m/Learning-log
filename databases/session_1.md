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

**Logical data independence** A software application must not break when a change occurs in a conceptual schema (e.g. new attributes added).

**Physical data independence** – neither a software application(s) nor a conceptual schema must be affected by changes at the physical level (i.e. new indexes, new access paths) because physical data organisation and access methods are not parts of application logic and code.

+

**Functional independence** – change in implementation (method used to execute a certain function) must not affect software applications.

## Users

- Database admins

- Database designers

- Software developers

- Business owners

- End users

 ## three-Schema Architecture
 
**External Schema/View** - individual user's view of the DB (shows relevant data, while hiding the other). Each application has its own host language (e.g. Java, PHP) and may have DBMS language embedded within the host language.

**Conceptual Schema/View** - a single integrated definition of the data within an enterprise which is unbiased toward any single application of data and is independent of how the data is physically stored or accessed. A database administrator is responsible for the maintenance of the conceptual schema. A formal definition of the logical structure of the database, often represented as an Entity-Relationship diagram.

**Internal Schema/View** – represents the actual storage of a database and defines records, indexes, files and other physical attributes. For every conceptual table there may be several actual storage files. The schema for the external and internal levels is kept by the database in its Data Dictionary, also know as the **Catalogue** or **System Tables**.
