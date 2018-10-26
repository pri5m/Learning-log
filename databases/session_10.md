
# Procedural SQL and Stored Procedures

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766723-dt-content-rid-11955795_2/courses/1819-CM6211/Week%204%20-%20Session%207%20-%20%20Procedural%20SQL%20%26%20Stored%20Procedures%281%29.pdf)

A procedural language extension to Structured Query Language (SQL). The purpose of PL/SQL is
to combine database language and procedural programming language.
A procedural language is a type of computer programming language that specifies a series of
well-structured steps and procedures within its programming context to compose a program. It
contains a systematic order of statements, functions and commands to complete a
computational task or program.

**Typical Added Features

➢ Declared constraints and variables

➢ Procedural language elements such as conditions and loops

➢Transaction control

➢Exception and error handling

## Advantages

➢It allows mixing SQL statements with procedural constructs.

➢It is possible to use blocks and subprograms to group SQL statements before sending them for
execution.

➢This improves traffic flow and improves response time.

➢Procedural SQL blocks can be compiled once and stored in executable form to improve
response time.

➢It provides functionality for decision making.

## PL/SQL vs T-SQL

PL/SQL (Procedural Language/Structured Query Language) is Oracle
Corporation's procedural extension for SQL and the Oracle relational database.

Transact-SQL (T-SQL) is Microsoft's and Sybase's proprietary extension to SQL.


PL/SQL is distinct from Transact-SQL, despite superficial similarities. Porting code from one to
the other usually involves non-trivial work, not only due to the differences in the feature sets of
the two languages, but also due to the very significant differences in the way Oracle and SQL
Server deal with concurrency and locking.

## Anonymous Block

Program units are the PL/SQL source code that is compiled, developed and ultimately executed
on the database.

The basic unit in PL/SQL is called a block, which is made up of three parts:

➢a declarative part (optional, defines and initialises constants and variables),

➢an executable part (required), and

➢an exception-handling part (optional, handles run time errors).

The keywords DECLARE, BEGIN, EXCEPTION, and END divide the block into a declarative part, an
executable part, and an exception-handling part.

If a variable is not initialized then it defaults to NULL value.
The block is not stored in the database, an, therefore, it is called an anonymous block (even if it
has a label).

*Anonymous Blocks are not supported in MySQL

## Stored procedure

A stored procedure is a segment of declarative SQL statements stored inside the database
catalog (schema). A stored procedure can be invoked by triggers, other stored procedures, and
applications such as Java, Python, PHP, etc.

**Characteristics:

1.Has a name.

2.May have in/out parameters.

3.Is stored in the schema.

4.Can be called by many users.
