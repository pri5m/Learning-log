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
