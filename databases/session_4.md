# Database design

## Database Development Life Cycle

➢DBDLC is inherently associated with the system development life cycle

➢As well as the system development life cycle it is not always sequential

➢It has feedback loops

➢DBDLC complexity depends on the complexity of the system it supports

## Initial study

Analyse company situation

The company situation describes the general conditions in which a company operates, its organizational structure, and its mission. To
analyse the company situation, the database designer must discover what the company's operational components are, how they
function, and how they interact.

Define problems and constraints

1. Examine formal and informal sources of data to identify BUSINESS RULES

2. How does the existing system functions?

3. What input does the existing system require and what documents/reports it generates?

4. What the output of the system is used for?

5. Who are the users of the system

Define objectives

What problems must the new system solve? What are the problem with the existing system? Why? Make sure that the requirements are
clear

Define scope and limitations

Make sure that the limitations of a DB are discussed, documented and understood by the client

## Business rules

Business rules are statements which describe the specifics of the organisation
operations.

Business rules are important because they underlie your database schema and define
the conditions it must meet. These are often implemented as 'Constraints‘.

Examples of business rules

➢Every Order must be associated with a valid Product as this prevents invalid Orders being entered into the
Database.

➢ A client may sign many contracts, but contract is signed by only one client.

➢A store employees many employees, but each employee is employed by only one store.

The rules must be understood by both clients and database designers.
When you extend your schema, keep the rules up-to-date.

Sources of information: mangers, business owners, written documentation, operation
manuals, interviews with end users

## Tips to capture better requirements

- Be prepared

- Ask fro relevent information and ask lots of why? How ill it improve the process.

- Note downin a clear form

- Create a description of requirements and constraints

## Three design phases

The three phases, schemas, and methods you use in a specific phase are as follows:

**Conceptual phase** As a database designer, in this phase, you collect all business requirements and rules in cooperation with
business domain experts. You create a conceptual schema by using the entity relationship (ER) method in this phase.
Alternatively, you could use Unified Modelling Language (UML). This stage is DBMS independent.

**Logical phase** During the logical phase, you represent data that is already grouped logically in entities by adding attributes and
relationships between entities. ER diagrams document this relational design. Logical phase also includes mapping to entities to
tables, functional dependency mapping and normalisation. This stage is DBMS dependent.

**Physical phase** You implement the relational model physically, in a database on a relational database management system
(RDBMS) such as MySQL, Oracle, Microsoft SQL Server etc. No matter which method you use for implementation (automatically
via a tool or manually), you have to prepare DDL statements for creating database objects in a language that your RDBMS
understands. This stage is DBMS dependent.

