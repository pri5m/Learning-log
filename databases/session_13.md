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

General structure of a transaction in a store proceedure:

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
