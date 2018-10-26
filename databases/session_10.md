
# Procedural SQL and Stored Procedures

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766723-dt-content-rid-11955795_2/courses/1819-CM6211/Week%204%20-%20Session%207%20-%20%20Procedural%20SQL%20%26%20Stored%20Procedures%281%29.pdf)

A procedural language extension to Structured Query Language (SQL). The purpose of PL/SQL is
to combine database language and procedural programming language.
A procedural language is a type of computer programming language that specifies a series of
well-structured steps and procedures within its programming context to compose a program. It
contains a systematic order of statements, functions and commands to complete a
computational task or program.

**Typical Added Features**

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

*Anonymous Blocks are not supported in MySQL*

## Stored procedure

A stored procedure is a segment of declarative SQL statements stored inside the database
catalog (schema). A stored procedure can be invoked by triggers, other stored procedures, and
applications such as Java, Python, PHP, etc.

**Characteristics:**

1.Has a name.

2.May have in/out parameters.

3.Is stored in the schema.

4.Can be called by many users.


## Advantages of stored procedures

➢Stored procedures help to increase the performance of the applications.

➢Stored procedures help to reduce the traffic between application and database server because
instead of sending multiple lengthy SQL statements, the application has to send only name and
parameters of the stored procedure.

➢Stored procedures are reusable and transparent to any applications. Stored procedures expose
the database interface to all applications so that developers don’t have to develop functions that
are already supported in stored procedures.

➢Stored procedures are secure. The database administrator can grant appropriate permissions to
applications that access stored procedures in the database without giving any permissions on
the underlying database tables.


## Disadvantages of stored procedures

➢If you use a lot of stored procedures, the memory usage of every connection that is using those
stored procedures will increase substantially. In addition, if you overuse a large number of logical
operations inside store procedures, the CPU usage will also increase because the database
server is not well-designed for logical operations.

➢Constructs of stored procedures make it more difficult to develop stored procedures that have
complicated business logic.

➢It is difficult to debug stored procedures (there are additional tools).

➢Developing and maintaining stored procedures requires a skill set that not all application
developers possess. 

## IN and OUT parameters in SP

The real power of stored procedures is
the ability to pass parameters and have
the stored procedure handle the differing
requests that are made.

**Types of Parameters**

1) IN type parameter: To send values to stored
procedures.

2) OUT type parameter: To get values from
stored procedures. This is similar to a return type
in functions.

3) IN OUT parameter: To send values and get
values from stored procedures.

*NOTE:* If a parameter type is not explicitly
defined, then by default is ‘IN’ type.

```
DROP PROCEDURE IF EXISTS MyFirstStoredProcedure;
-- GENERAL STUCTURE OF a SP

DELIMITER $$

CREATE PROCEDURE MyFirstStoredProcedure ()
BEGIN

-- The executable part
SELECT 'Database Systems' as 'My favorite module is';

END$$

DELIMITER ; 
```

```
CREATE PROCEDURE ReportOnModuleMarksPerModuleOUT (IN SpecificModuleCode int, OUT HighestMark DOUBLE, OUT LowestMark DOUBLE)
BEGIN

SELECT m.moduleTitle, MIN(a.finalMark) as LowestMark, MAX(a.finalMark) as HighestMark, CAST(AVG(a.finalMark) as DECIMAL(4,2))  as AverageMark
FROM assignments a
INNER JOIN modules m ON m.moduleCode=a.moduleCode
WHERE m.moduleCode = SpecificModuleCode -- this SQL query references the input parameter 
GROUP BY m.moduleCode;

// INTO puts the output of this query into the defined OUT parameter
SELECT MIN(a.finalMark) INTO LowestMark
FROM assignments a
INNER JOIN modules m ON m.moduleCode=a.moduleCode
WHERE m.moduleCode = SpecificModuleCode -- this SQL query references the input parameter 
GROUP BY m.moduleCode;


SELECT MAX(a.finalMark) INTO HighestMark
FROM assignments a
INNER JOIN modules m ON m.moduleCode=a.moduleCode
WHERE m.moduleCode = SpecificModuleCode -- this SQL query references the input parameter 
GROUP BY m.moduleCode;


END//

DELIMITER ;

```

## Type of Variables in MySQL

➢ Local variables

Local variables are set in the scope of a statement or block of statements.Once that statement or block of
statements has completed, the variable goes out of scope.

➢Session variables

Session variables are set in the scope of your session with the MySQL server.A session starts with a
connection to the server and ends when the connection is closed. Variables go out of scope once the
connection is terminated. Variables created during your connection cannot be referenced from other
sessions.To declare or reference a session variable, prefix the variable name with an @ symbol:

```SET @session_variable = 100;```

➢Global variables

Global variables exist across connections. They are set using the GLOBAL keyword:

```SET GLOBAL max_connections = 300;```

## Local Variable DECLARE Syntax

Stored programs can use DECLARE to define local variables
Variable declarations must appear before cursor or handler declarations.
Syntax:

```DECLARE var_name [, var_name] ... type [DEFAULT value]```

This statement declares local variables within stored programs. To provide a default value for a variable,
include a DEFAULT clause. The value can be specified as an expression; it need not be a constant. If
the DEFAULT clause is missing, the initial value is NULL.

The scope of a local variable is the BEGIN ... END block within which it is declared. The variable can be
referred to in blocks nested within the declaring block, except those blocks that declare a variable with the
same name.

A local variable should not have the same name as a table column.

Variables can be set directly with the SET statement.

## Declaring Variables

To declare variable:

```DECLARE variable_name datatype(size) DEFAULT default_value;```

To set variable:

```SET variable_name = value;```

Example:
```
DECLARE totalCount INT DEFAULT 0;
SET totalCount = 10;
```

## Conditional statements

```
IF expression THEN
SQL statements;
ELSEIF elseif-expression THEN
SQL elseif-statements;
...
ELSE
SQL else-statements;
END IF;
```

You can use EXISTS condition in IF statement
```
IF
EXISTS (SELECT customerID FROM customers WHERE username=NewUsername)
THEN
SELECT ‘Customer Already Exists’;
ELSE
SELECT ‘No Customers’;
END IF;
```

```
DROP procedure IF EXISTS ReportOnModuleMarksAllAndPerModule;
DELIMITER //ReportOnModuleMarksAllAndPerModule

// Takes int modulel amrk in as parameter
CREATE PROCEDURE ReportOnModuleMarksAllAndPerModule (SpecificModuleCode int)
BEGIN

//If true, null is input parameter it will return a report of all the modules
IF ISNULL(SpecificModuleCode) THEN

SELECT m.moduleTitle, MIN(a.finalMark) as LowestMark, MAX(a.finalMark) as HighestMark, CAST(AVG(a.finalMark) as DECIMAL(4,2))  as AverageMark
FROM assignments a
INNER JOIN modules m ON m.moduleCode=a.moduleCode
GROUP BY m.moduleCode;

ELSE

// Calls another store procedure
// Will provide a report for that particular module code 
CALL ReportOnModuleMarksPerModule(SpecificModuleCode);

END IF;
END//
DELIMITER ;
```
