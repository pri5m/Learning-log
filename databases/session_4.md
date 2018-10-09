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
