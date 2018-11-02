# Transaction

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766725-dt-content-rid-11996558_2/courses/1819-CM6211/Week%205%20-%20Session%2013%20-%20Transactions%20and%20Locks.pdf)

A unit of work that is performed againsta database.

A transaction

➢ groups SQL queries and statements, and executes them together;

➢ ensures data integrity and handles databaseerrors;

➢ hasACIDproperties.


## “ACID” Propertiesof aTransaction

RDBMSs are ACID

Atomicity -ALL operations within a transaction are completedsuccessfully; otherwise,
the transaction is aborted at the point of failure, and previous operations are rolled
backto theirformerstate.

Consistency-All operationstransformthe databasefromone consistentstateto another
consistent state (no data integrity or referential integrity constraints violations).

Isolation- transactionsoperate independently of andarenottransparentto each
other until they arecommitted.

Durability-the result of acommittedtransaction persistsin caseof asystem failure.

## Transaction control

**START TRANSACTION** – starts a new transaction.

**COMMIT** - saves changes invoked by a transaction to the database. It saves all changes to the
database since the last COMMIT or ROLLBACKcommand.

**ROLLBACK** – the command used to undo transactions that have not already been saved to the
database. The ROLLBACK command can only be used to undo transactions since the last
COMMIT or ROLLBACK command wasissued.

**SAVEPOINT** - create points within a transaction to which to ROLLBACK. A SAVEPOINT is apoint
in a transaction when you can roll the transaction back to a certain point without rolling back
the entire transaction.
```
SAVEPOINT SAVEPOINT_NAME;
ROLLBACK TO SAVEPOINT_NAME;
```

**RELEASE SAVEPOINT** - removes a SAVEPOINT that you havecreated.
```
RELEASE SAVEPOINT SAVEPOINT_NAME;
```

**SET autocommit** - disables or enables the default autocommit mode for the currentsession.

### Autocommit

Bydefault, MySQLruns with autocommit mode enabled. This means that as soon as you execute a
statement that updates (modifies) a table, MySQLstores the update on disk to make it permanent.
Thechangecannot be rolledback.
Todisable autocommit mode implicitly for asingle seriesof statements, usethe START
TRANSACTIONstatement:

```
START TRANSACTION;
SELECT @A:=SUM(salary) FROM table1 WHEREtype=1;
UPDATEtable2 SET summary=@A WHERE type=1;
COMMIT;
```

With START TRANSACTION, autocommit remains disabled untilyou end the transaction
with COMMITor ROLLBACK.Theautocommit mode then reverts to its previous state.

SETautocommit=0;

After disabling autocommit mode by setting the autocommit variable tozero,
changes to transaction-safe tables (such as those for InnoDB ) are not made
permanent immediately. You must use COMMIT to store your changes to disk
or ROLLBACK to ignore thechanges.

autocommit is a session variable and must be set for eachsession.

### Start transaction

Beginning a transaction causes any pending transaction to becommitted.

Beginning a transaction also causes table locks acquired with LOCK TABLES to be released,
as though you have executed UNLOCK TABLES

### ROLLBACK TO savepoint

The ROLLBACK TO SAVEPOINTstatement rolls back a transaction to the named savepoint without
terminating the transaction.

Modifications that the current transaction made to rows after the savepoint was set are undone in the
rollback, but InnoDBdoes not release the row locks that were stored in memory after the savepoint.
Savepoints that were set at a later time than the named savepoint aredeleted.

The RELEASE SAVEPOINTstatement removes the named savepoint from the set of savepoints of the current
transaction. No commit or rollbackoccurs.

All savepoints of the current transaction are deleted if you execute a COMMIT, or a ROLLBACKthat does not
name a savepoint.

## Implicit commit

➢Data definition language (DDL) statements that define or modify database objects.
CREATE DATABASE, CREATE INDEX, CREATE PROCEDURE, CREATE TABLE,
CREATE TRIGGER, CREATE VIEW, DROP DATABASE, DROP EVENT, DROP
INDEX, DROP PROCEDURE, DROP SERVER, DROP TABLE,DROP TRIGGER, DROP
VIEW,

➢Statements that implicitly use or modify tables in the mysqldatabase. ALTER USER,
CREATE USER, DROP USER, GRANT, RENAME USER, REVOKE, SET PASSWORD,

➢Transaction-control and locking statements. LOCK TABLES,
SET autocommit = 1 (if the value is not already 1), START TRANSACTION,
UNLOCK TABLES.

## When are changes commited?

Transactions complete with one of the following events:

➢A COMMIT statement makes the changes to the database permanent.

➢A ROLLBACK statement undoes all the changes made by the transaction.

➢A statement with a side effect of an automatic commit is executed: data definition commands,
such as ALTER, CREATE, COMMENT, and DROP all have the side effect of an automatic commit.

➢A disconnection from a database performs an implicit rollback.

➢ODBC and JDBC have an autocommit setting that enforces a COMMIT after each statement. By
default, ODBC and JDBC require autocommit to be on, and each statement is a single
transaction. If you want to take advantage of transaction design possibilities, then you should
turn autocommit off.

#### General structure of a transaction in a store proceedure:

```
BEGIN . .
DECLARE variables . .
DECLARE exit handler for sqlexception
BEGIN …. ROLLBACK; END;
STARTTRANSACTION;
SQL Query 1…
..
SQL Query N…
COMMIT;
END
```

To perform a
ROLLBACK in MySQL
Stored Procedure, you
must declare an exit
handler in the stored
procedure. 

#### MySQL JDBC Transaction

```
try
{
Connection con = DriverManager.getConnection(dbURL,dbUser,dbPassword);
con.setAutoCommit(false);
// perform operations such as insert, update, delete here
// if everything is OK, commit the transaction
con.commit();
} catch(SQLException e){
// in case of exception, rollback the transaction
con.rollback();
}
```

### Error handling

When an error occurs inside astored procedure, it is important to handle it appropriately, suchas
continuing or exiting the current code block’s execution, and issuingameaningful error message.

```DECLARE action HANDLER FOR condition_value statement;```

action:

• CONTINUE : the execution of the enclosing code block ( BEGIN …END )continues.

• EXIT: the execution of the enclosing code block, where the handleris declared, terminates.

condition_value:

• A MySQL error code.

• A standard SQLSTATE value (SQLWARNING , NOTFOUND orSQLEXCEPTION)

• A named condition associated with either a MySQL error code orSQLSTATE value.

### Handlers

```
DECLARE e x i t handler f o r sqlexception
BEGIN
- - Handle an sql EXCEPTION
ROLLBACK;
END;
DECLARE e x i t handler f o r sqlwarning
BEGIN
- - Handle an sql WARNING
ROLLBACK;
END;
```

## Concurrency Control

The ability of multiple operations (in database terminology, transactions)
to run simultaneously, without interfering with each other. Concurrency is
also involved with performance, because ideally the protection for multiple
simultaneous transactions works with a minimum of performance overhead,
using efficient mechanisms for locking.

### Schedule

Schedules and schedule properties are fundamental concepts in database concurrency
control theory.

Schedule - the chronological sequence in which the component operations of the different
transactions are executed. A schedule can have many transactions in it, each comprising of a
number of statements.

To process transactions concurrently, the database server must execute some statements of one
transaction, then some statements from other transactions, before continuing to process further
operations from the first. Applying transactions concurrently can result in inconsistencies.

### Typical types of inconsistency

**Dirty read:** Transaction A modifies a row, but does not commit or roll back the change. Transaction B reads the
modified row. Transaction A then either further changes the row before performing a COMMIT, or rolls back its
modification. In either case, transaction B has seen the row in a state which was never committed.

**Non-repeatable read:** Transaction A reads a row. Transaction B then modifies or deletes the row and performs a
COMMIT. If transaction A then attempts to read the same row again, the row will have been changed or deleted.

**Phantom row:** (or Phantom Read) Transaction A reads a set of rows that satisfy some condition. Transaction B
then executes an INSERT or an UPDATE on a row which did not previously meet A's condition. Transaction B
commits these changes. These newly committed rows now satisfy Transaction A's condition. If Transaction A then
repeats the read, it obtains the updated set of rows.

**Lost update:** This might happen if Transactions A first reads in value into a variable and then uses the variable in
an update statement in a later step. When this update executes, Transaction B updates the same data. Whichever
of these transactions in committed first becomes a lost update because it was replaced by the second update.

The inconsistency appears because of the way the statements were interleaved; the result produced would not
be possible if all transactions were executed sequentially.

### Serializability

Serializability is the classical concurrency scheme. It ensures that a schedule for executing
concurrent transactions is equivalent to one that executes the transactions serially in some
order. It assumes that all accesses to the database are done using read and write operations. A
schedule is called ``correct'' if we can find a serial schedule that is ``equivalent'' to it. Given a set
of transactions T1...Tn, two schedules S1 and S2 of these transactions are equivalent if the
following conditions are satisfied:

➢Read-Write Synchronization: If a transaction reads a value written by another transaction in one
schedule, then it also does so in the other schedule.

➢Write-Write Synchronization: If a transaction overwrites the value of another transaction in one
schedule, it also does so in the other schedule.

These two properties ensure that there can be no difference in the effects of the two schedules.

Serializability is the commonly accepted criterion for correctness. A serializable schedule is
accepted as correct because the database is not influenced by the concurrent execution of the
transactions.

### Types of scheduals

*Several questions*

There are different types of schedules:

Serial Schedule − transactions are executed in a serial manner, one after another.

Serializable Schedule - a schedule that is equivalent (in its outcome) to a serial schedule. It is
said to have the serializability property. Knowing that a schedule is serializable does not settle in
which order transactions would best be executed, but rather states that concurrency has added
no effect.

Non-serializable Schedule – is a schedule that introduces various inconsistencies due to
concurrent execution of transaction.

### Transaction isolation

*Several questions*

There are several isolation levels available in MySQL, that help to avoid inconsistencies:

➢NONE – puts no restrictions on the read and updates to the database.

➢READ UNCOMMITTED - Allows uncommitted changes by one transaction to be readable by other
transactions. SELECT statements are performed in a nonlocking fashion, but a possible earlier version
of a row might be used. Thus, using this isolation level, such reads are not consistent. This is also
called a dirty read. Otherwise, this isolation level works like READ COMMITTED.

➢READ COMMITED – makes all updates to a table invisible to all other transactions until a commit is
performed.

➢REPEATABLE READ – keeps all SELECT consistent in a single transaction.

➢SERIALIZABLE – causes all read and updates to operate in a serialized sequence

## Locking

The system of protecting a transaction from seeing or changing data that
is being queried or changed by other transactions.
The locking strategy must balance reliability and consistency of
database operations (the principles of the ACID philosophy) against
the performance needed for good concurrency.

Use locking for cooperating table access between sessions.

### Locking in MySQL

MySQL allows a client session to acquire a table lock explicitly for preventing other sessionsfrom
accessing the table during a specific period. A client session can acquire or release table locks
only for itself. It cannot acquire or release table locks for other sessions.

SQL statement for locking a table

```LOCK TABLES table_name [READ | WRITE]```

MySQL provides two lock types: ```READ``` and ```WRITE```.
SQL statement for unlocking a table:

```UNLOCK TABLES;```

**You could not use LOCKs in storedprocedures!**

The correct way to use LOCKTABLESand UNLOCK TABLESwith transactional tables,such
as InnoDB tables, is to begin a transaction with SET autocommit = 0 (not START TRANSACTION)
followed by LOCK TABLES, and to not call UNLOCK TABLESuntil you commit the transaction
explicitly.

### Require locks within a transaction

Atransaction commit or rollback releases alllocks.

When autocommit is enabled (default) acquiring a lock outside thetransaction has no
effect. Because a commit is made at the end of each statement and acquired lock
immediatelyreleased.

## Deadlock

A deadlock is a concurrency issue.

A situation where different transactions are unable to proceed, because each holds a lock that the
other needs.Becauseboth transactions are waiting for aresourceto becomeavailable,neither will
ever release the locks it holds.

A deadlock can occur when the transactions lock rows in multiple tables (through statements such
as UPDATE or SELECT ... FOR UPDATE), but in the opposite order. A deadlock can also occur when
such statements lock ranges of index records and gaps, with eachtransaction acquiring some locks
but not others due to atiming issue.

InnoDB detects deadlocks.

### Minimizing deadlocks

*Deadlocks cannot be completely avoided!*

➢Use as few locks as possible

➢ Reduce locking required for atransaction

➢Usesmaller (shorter) transactions (a lock will only hold for the duration of a
transaction)

➢Access objects in the sameorder

➢Avoid user interaction in transactions (If a transaction is waiting for user input and
the user goes to lunch or even home for the weekend, the user delays the transaction
from completing)

# Session code
```sql
DROP SCHEMA IF EXISTS `university` ;


CREATE SCHEMA `university`;

USE university; -- or double click the database name in the Navigator on your left


DROP TABLE IF EXISTS students;

-- Let's create a new table now
CREATE TABLE students ( studentID int PRIMARY KEY,
                        FirstName varchar(50),
                        Surname varchar(50),
                        MobileNumber varchar(20),
                        DOB date,
                        Registered boolean, -- 1 for registered (TRUE) and 0 for not registered (FALSE)
                        RegisteredOn timestamp
					   ) ENGINE=INNODB;
                         


INSERT INTO students VALUES ('1', 'Amie', 'Hall', '078658887671', '1993-02-26' ,0,NOW());
INSERT INTO students VALUES ('2', 'Mark', 'Jones', '09234817674', '1994-05-29' ,0,NOW());
INSERT INTO students VALUES ('3', 'Leanne', 'King', '0345387676', '1993-12-22' ,0,NOW());
INSERT INTO students VALUES ('4', 'Martin', 'Munn', '0450878887634', '1992-11-05' ,1,NOW());
INSERT INTO students VALUES ('5', 'Gareth', 'Cooper', '0760878887672', '1992-10-02' ,0,NOW());
INSERT INTO students VALUES ('6', 'Kian', 'Smith', '0890871887676', '1992-11-07' ,1,NOW());
INSERT INTO students VALUES ('7', 'Max', 'Marks', '0897817623', '1995-03-12' ,1,NOW());
INSERT INTO students VALUES ('8', 'Matthew', 'Arnold', '0897817623', '1991-01-19' ,1,NOW());
INSERT INTO students VALUES ('9', 'Claire', 'Cooper', '05643227623', '1992-12-31' ,1,NOW());
INSERT INTO students VALUES ('10', 'Madeline', 'Bergman', '034317623', '1991-01-23' ,TRUE,NOW());
INSERT INTO students VALUES ('11', 'Matthew', 'Anderson', '02343227623', '1992-10-21' ,FALSE,NOW());
INSERT INTO students VALUES ('12', 'Stuart', 'Ali', '0234457623', '1995-05-11' ,FALSE,NOW());
INSERT INTO students VALUES ('13', 'Sam', 'Allen', '02343227623', '1994-10-01' ,FALSE,NOW());
INSERT INTO students VALUES ('14', 'Stuart', 'Armstrong', '07673227623', '1993-12-11' ,FALSE,NOW());
INSERT INTO students VALUES ('15', 'Alfie', 'Armstrong', '045564227623', '1994-11-11' ,FALSE,NOW());
INSERT INTO students VALUES ('16', 'Ben', 'Armstrong', '09863227623', '1992-09-23' ,FALSE,NOW());
INSERT INTO students VALUES ('17', 'Frank', 'Armstrong', '0454227623', '1992-07-29' ,FALSE,NOW());


CREATE TABLE lecturers
(
lecturerID int NOT NULL AUTO_INCREMENT,
lecturerName varchar(50) NOT NULL,
lecturerSurname varchar(50),
spinepoint smallint NULL,
CONSTRAINT lecturers_PK PRIMARY KEY (lecturerID)
) ENGINE=INNODB;

-- pupulate table lecturers
INSERT INTO lecturers  VALUES (1, 'Julia', 'Williams',34);
INSERT INTO lecturers  VALUES (2, 'James', 'Edwards',35); 
INSERT INTO lecturers  VALUES (3, 'Joanna', 'Holms',37);
INSERT INTO lecturers (lecturerName,lecturerSurname,spinepoint)  VALUES ('Emilia', 'King',35);
INSERT INTO lecturers (lecturerName,lecturerSurname,spinepoint)  VALUES ('Molly', 'Kettle',37);
INSERT INTO lecturers (lecturerName,lecturerSurname,spinepoint)  VALUES ('Archie', 'Davies',NULL);
INSERT INTO lecturers (lecturerName,lecturerSurname,spinepoint)  VALUES ('Devon', 'Lloyd',NULL);

-- CREATE NEW TABLE Modules (PK_ModuleCode, ModuleTitle, FK_LecturerID)

CREATE TABLE modules
( moduleCode int NOT NULL,
  moduleTitle char(255) NOT NULL,
  lecturerID int NULL, -- Note is could be set to NULL (i.e. the module has not been allocated yet)
  startDate date NULL DEFAULT '2016-10-01',
  endDate date NULL DEFAULT '2017-01-21',
  credit smallint NOT NULL,
  CONSTRAINT modules_pk PRIMARY KEY (moduleCode),
  CONSTRAINT fk_lecturers
      FOREIGN KEY (lecturerID)  
      REFERENCES lecturers(lecturerID)  -- PK and FK must be of the same data type and of the same size!
  ON DELETE CASCADE
  ON UPDATE CASCADE
  ) ENGINE=INNODB;

-- Populate the table
INSERT INTO modules  VALUES (111, 'Database Systems', '1','2016-10-01','2017-01-21',10);
INSERT INTO modules  VALUES (888, 'Database Systems', '1','2017-10-01','2018-01-21',10);
INSERT INTO modules  VALUES (222, 'Agile Development', '3','2017-10-01','2018-10-01',20); 
INSERT INTO modules  VALUES (333, 'Java', '2','2017-10-01','2018-10-01',20); 
INSERT INTO modules  VALUES (444, 'Group Project', '2','2017-10-01','2018-10-01',20);  
INSERT INTO modules  VALUES (555, 'Advanced Database Systems', '2','2017-10-01','2018-01-21',10); 
INSERT INTO modules  VALUES (999, 'Advanced Database Systems', '2','2018-10-01','2019-01-21',10); 
INSERT INTO modules  VALUES (777, 'DevOp', '3','2018-10-01','2019-01-21',10); 

-- drop table assignments;

-- We need a linking table Assignments 
-- to resolve Many-to-Many relationships 
-- between Students and Modules
CREATE TABLE assignments 
(
studentID int NOT NULL,
moduleCode int NOT NULL,
assignedON date NOT NULL,
completed boolean NOT NULL DEFAULT 0,
finalMark int,
-- NOTE - we declare a composite primary key!
CONSTRAINT assignments_pk PRIMARY KEY (studentID,moduleCode),
CONSTRAINT fk_students
      FOREIGN KEY (studentID)  
      REFERENCES students(studentID),
CONSTRAINT fk_modules
      FOREIGN KEY (moduleCode)  
      REFERENCES modules(moduleCode)
    
  ON DELETE CASCADE
  ON UPDATE CASCADE
) ENGINE=INNODB;


INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(13,222,DATE(now()),50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(14,333,'2016-03-12',100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(12,333,'2016-03-12',30);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(3,888,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(5,888,DATE(now()),40);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(14,888,'2016-06-12',50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(15,111,DATE(now()),50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(13,555,'2016-06-12',50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(12,777,DATE(now()),50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(1,222,'2016-06-12',100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(5,333,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(5,111,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(13,111,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(9,111,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(4,111,DATE(now()),50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(7,111,DATE(now()),50);



/*
***************************************************
***************************************************
                TRANSACTIONS
***************************************************
***************************************************
*/

-- WE START HERE --

USE university;


-- Default setting of autommit is 1 - i.e. it is ON by default
-- All operations will be commited straight away
-- SET autocommit=1; -- ON
-- SET autocommit=0; -- OFF


show global variables like 'autocommit';

SELECT * from students;

UPDATE students
SET FirstName = "Chris"
WHERE studentID>=2;

SELECT * FROM students;

-- No changes could be rolled back as all changes have been commited immediately
ROLLBACK;

-- Re-create the schema 
SELECT * FROM students;

-- SET autcommit mode to OFF
SET autocommit=0; -- OFF

SELECT * from students;

UPDATE students
SET FirstName = "Yulia"
WHERE studentID>0;

SELECT * from students;

-- ALL changes will be rolled back
ROLLBACK;

-- No changes were made to the database
SELECT * from students;


-- Let's execute a set of commands
SET autocommit=0; -- OFF

INSERT INTO modules  VALUES (567, 'Adopting Technology', '2','2017-10-01','2018-01-21',10);
SAVEPOINT NewModule;
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(3,567,DATE(now()),100);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(5,567,DATE(now()),40);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(14,567,'2016-06-12',50);
INSERT INTO assignments(studentID, moduleCode, assignedON,finalMark) VALUES(15,567,DATE(now()),50);
SELECT * FROM modules WHERE moduleCode=567;
SELECT * FROM assignments WHERE moduleCode=567;

ROLLBACK TO NewModule;


-- check the result 
SELECT * FROM modules WHERE moduleCode=567;
SELECT * FROM assignments WHERE moduleCode=567;

-- When I am sure that everything is correct I will COMMIT my changes

COMMIT;

SELECT * FROM modules WHERE moduleCode=567;
SELECT * FROM assignments WHERE moduleCode=567;





-- FINALLY, set autocommit to 1 (ON) back again
SET autocommit=1; -- ON

-- This is a stored procedure which increases the spinepoints of our lecturers
-- by a given number of points
DELIMITER $$

CREATE PROCEDURE updateSpinepoints (increaseBy Int)
BEGIN

DECLARE MinLecturerID int;
DECLARE MaxLecturerID int;
DECLARE i int;

SET  MinLecturerID = (SELECT MIN(lecturerID) FROM lecturers);
SET  MaxLecturerID = (SELECT MAX(lecturerID) FROM lecturers);
SET i=MinLecturerID;

WHILE i<=MaxLecturerID DO

IF (SELECT COUNT(*) FROM lecturers WHERE lecturerID=i)<>0 THEN
	
    UPDATE university.lecturers
	SET spinepoint = spinepoint + increaseBy 
	WHERE lecturerID=i;
    
	SET i=i+1;
ELSE
	SET i=i+1;
END IF;
END WHILE;

END$$

DELIMITER ;


SELECT * FROM lecturers;

CALL updateSpinepoints(1);

SELECT * FROM lecturers;



-- This is a stored procedure which increases the spinepoints of our lecturers
-- by a given number of points
-- We will now put all changes into a transaction
-- which means that either all spinepoints must are updated or none

-- We now changes the stored procedures so that it checks for NULLs in the spinepoint column
-- and rolls back a transaction if a NULL is found

DELIMITER $$

DROP PROCEDURE IF EXISTS updateSpinepointsTransaction $$

CREATE PROCEDURE updateSpinepointsTransaction (increaseBy Int)
BEGIN
    
DECLARE MinLecturerID int;
DECLARE MaxLecturerID int;
DECLARE i int;
DECLARE Success Boolean;
SET Success = TRUE;

SET  MinLecturerID = (SELECT MIN(lecturerID) FROM lecturers);
SET  MaxLecturerID = (SELECT MAX(lecturerID) FROM lecturers);
SET i=MinLecturerID;

START TRANSACTION;

	MyWhileBlock:
	WHILE i<=MaxLecturerID DO

		IF (SELECT COUNT(*) FROM lecturers WHERE lecturerID=i)<>0 THEN
			
			IF (SELECT spinepoint FROM lecturers WHERE lecturerID=i) IS NULL THEN
					SET Success = FALSE;
					LEAVE MyWhileBlock;
					
			ELSE 
			
					UPDATE university.lecturers
					SET spinepoint = spinepoint + increaseBy 
					WHERE lecturerID=i;
					SET i=i+1;
			END IF;  
		ELSE
			SET i=i+1;
		END IF;
	END WHILE MyWhileBlock;

	IF Success = FALSE THEN
		ROLLBACK;
		SELECT "Transaction has been rolled back because the initial values of spinepoints are unknown for some lecturers." as Message;
	ELSE
		COMMIT;
		SELECT CONCAT("Transaction has been commited. All spinepoints have been incremented by ", increaseBy, " spinepoints.") as Message;
	END IF;

END$$

DELIMITER ;

-- More about blocks in MySQL
-- http://dev.mysql.com/doc/refman/5.7/en/begin-end.html
-- http://dev.mysql.com/doc/refman/5.7/en/statement-labels.html


SELECT * FROM lecturers;

-- Increase all spinepoints, but ONLY if ALL spinepoints are known;
CALL updateSpinepointsTransaction(3);

SELECT * FROM lecturers;

-- Change the table to remove all NULLS from the columns spinepoints and re-run the stored procedures

CALL updateSpinepointsTransaction(1);

SELECT * FROM lecturers;

-- We will now create a stored procedure for updating spinepoints
-- with the use of a handler. (Note this SP does not include a check for NULLs)

DELIMITER $$

CREATE PROCEDURE updateSpinepointsWithHandler (increaseBy Int)
BEGIN

DECLARE MinLecturerID int;
DECLARE MaxLecturerID int;
DECLARE i int;
DECLARE Success Boolean;

DECLARE EXIT HANDLER FOR SQLEXCEPTION 
    BEGIN
        ROLLBACK;
        SELECT "Transaction has been rolled back because an SQL execption has occured!" as Message;
     END; 



START TRANSACTION;

	SET  MinLecturerID = (SELECT MIN(lecturerID) FROM lecturers);
	SET  MaxLecturerID = (SELECT MAX(lecturerID) FROM lecturers);
	SET i=MinLecturerID;

	WHILE i<=MaxLecturerID DO

		IF (SELECT COUNT(*) FROM lecturers WHERE lecturerID=i)<>0 THEN
			
					UPDATE university.lecturers
					SET spinepoint = spinepoint + increaseBy 
					WHERE lecturerID=i;
					SET i=i+1;
		   
		ELSE
			SET i=i+1;
		END IF;
	END WHILE;

	-- SELECT * FROM lecturers;

	-- This will give an error because there is no such table
	INSERT INTO SpinePointUpdates (UpdateDate, EmployeeID, IncreaseBy) VALUES (now(), 23434, increaseBy);

COMMIT;

SELECT "Transaction has been commited";

END$$

DELIMITER ;


CALL updateSpinepointsWithHandler(1);

-- Let's create the table SpinePointUpdates
CREATE TABLE SpinePointUpdates (UpdateDate TIMESTAMP, EmployeeID int, IncreaseBy int);

SELECT * FROM lecturers;

-- and execute our stored procedure again
CALL updateSpinepointsWithHandler(3);

SELECT * FROM lecturers;
SELECT * FROM SpinePointUpdates;

-- A TASK FOR YOU: WRITE A NEW STORED PROCEDURE
-- The new stored procedure must create a new module and assign all registered students to it.
-- Module Code and Module title must be passed to the SP as the input parameters (you can choose at your discretion and hard-code all other required values).
-- The new SP must contain a transaction to wrap up all CREATE and INSERT SQL statements.
-- Create an exit handler for an error with CODE 1062 which is a duplicate keys error with a customised error message. 
-- The handler must roll back all changes.
-- Create a handler for all SQL exceptions.
-- The handler must roll back all changes.

-- Test your SP by creating a new module called "Adopting Technology" with module code 567,
-- and then a new module called "Emerging Technology" with module code 687.



/*
***************************************************
                     LOCKS
***************************************************
*/

-- Find out the current connection id, use the CONNECTION_ID()
SELECT CONNECTION_ID();

-- %%%%%% READ LOCK
-- Lock the table students
LOCK TABLE students READ;

SELECT * FROM students;

-- You  will get an error message, once READ lock is acquired, you cannot write data into the table within the same session.
INSERT INTO students VALUES ('45', 'Matthew', 'Anderson', '02343227623', '1992-10-21' ,FALSE,NOW());

-- You can see the detailed information from the SHOW PROCESSLIST statement.
SHOW PROCESSLIST;


-- CREATE a NEW SESSION  - create a new connection and attempt to read and write into the same table

UNLOCK TABLES;

-- You can see the detailed information from the SHOW PROCESSLIST statement.
SHOW PROCESSLIST;





-- %%%%%% WRITE LOCK
	
LOCK TABLE students WRITE;

SELECT * FROM students;

INSERT INTO students VALUES ('554', 'Matthew', 'Anderson', '02343227623', '1992-10-21' ,FALSE,NOW());

-- check the state
SHOW PROCESSLIST;


-- CREATE a NEW SESSION  - create a new connection and attempt to read and write into the same table

-- release the lock	
UNLOCK TABLES;


-- Go back to the SP that you have created earlier in this session
-- (a transaction for creating a new module and assignments for the module)
-- Alter the code now to include acquiring write locks on both tables involved before running the inset statements. DO NOT forget the release the locks!!!



/*
***************************************************
                     ISOLATION LEVELS
***************************************************
*/

DROP SCHEMA IF EXISTS ex_locks;
CREATE SCHEMA ex_locks; 
USE ex_locks;


DROP TABLE IF EXISTS serializability;

CREATE TABLE serializability (id INT NOT NULL PRIMARY KEY, 
                              some_value INT NOT NULL);

INSERT INTO    serializability VALUES (1, 1);
INSERT INTO    serializability VALUES (2, 2);

SELECT * FROM serializability;


SELECT CONNECTION_ID();

-- READ COMMITTED

SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
SET autocommit = 0;

-- READ COMMITED – makes all updates to a table invisible to all other transactions until a commit is performed.

SELECT * FROM serializability where some_value = 2;
UPDATE  serializability SET some_value = 1 WHERE id = 2;
SELECT * FROM serializability;

--  Now open another connection and run these lines of code:
SELECT CONNECTION_ID();
SELECT * FROM serializability;

-- Return to the first connection COMMIT and then check the output in the second transaction again
Commit;

-- https://dev.mysql.com/doc/refman/5.5/en/innodb-transaction-isolation-levels.html


```
