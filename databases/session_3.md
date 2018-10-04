# Database normalisation

04/10/18

[Session slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766717-dt-content-rid-11793831_2/courses/1819-CM6211/Week%203%20-%20Session%204%20-%20Database%20Normalisation.pdf)

## Refactoring your database

➢Table must represent only one subject of the Universe of Discourse

➢ Field must represent only one specific characteristic of the subject

➢ Each field must contain only one value (no multipart or multivalued fields)

➢ Do not store the results of calculations (they are not updated automatically)

➢ Column (field) name must appear only once in the database

➢ There should not be any (unnecessary) duplicated fields

## Data anomalies

**Update anomalies** − updating a piece of data in one place does not update the copies of this
data stored in other places in the database (redundant data).

**Deletion anomalies** − deletion of data leaves some part(s) of the data because of unawareness
about it, or unintended loss of data due to deletion of other data.

**Insert anomalies** − inability to add data to the database due to absence of other data.

## Database normalisation

The process of redesigning the model to unbundle any overlapping entities in order to avoid
insertion, deletion and update anomalies so that redundancy and inconsistency are avoided.

**Normalization is a method to remove all anomalies and bring the database to a consistent state.**

To normalise a relation you must decompose it into several smaller relations.
In a normalised (well-formed) relation there are no insertion, deletion and update anomalies.

### Benefits

➢Easier to understand your data because data is organised logically

➢Data integrity as eliminates redundancy and inconsistency, and enforces referential integrity.

➢More optimal storage due to reduced data duplication.

➢Improved performance (faster to write and to access than a poorly designed database)

- Optimised queries

- Faster index creation and sorting (because tables have fewer columns)

### Functional dependency

A **functional dependency** is a relationship (dependency) between two attributes in a relation where
the value of one attribute determines the value of another attribute (or set of attributes).

```
CourseStartYear + CourseDuration = CourseEndYear
2016 + 3 = 2019
studentID → studentName, studentSurname, studentDOB
```
Primary key and candidate key functionally determine all other non-key attributes

Functional dependency is represented by an arrow sign →

e.g. ```X→Y```, means X functionally determines Y, where X a determinant. 

### Normalisation Rules

- Every determinant must be a candidate key

- A relation that is not well-formed MUST BE SPLIT into two or more well-formed relations

**REMEMBER:** A relation must represent one and only one Entity of the Universe of Discourse!

## Normalisation process

1. Remove repeating groups

2. Remove partial dependencies

3. Remove transitive dependencies

4. Make sure every determinant is a candidate key

5. Remove Multi-Valued dependencies

6. Remove Join dependencies

### First Normal form (1NF)

The requirement a relation should satisfy to be in 1NF:

- No multivalued attributes (Remember the properties of a relation: Every cell must contain a single value!)

By definition, ALL relations are in 1NF

### Second normal form (2NF)

The requirements a relation should satisfy to be in 2NF:

- No multivalued attributes, i.e. it MUST BE in 1NF
(Remember: Every cell must contain a single value!)

AND

- No partial dependencies (every non-key attribute must be fully
functionally dependent on the ENTIRE primary key)

### Partial dependency

Partial dependency is a dependency of non-key attributes on a part of the primary key.

Partial dependency may ONLY happen when you have a composite primary key.

### Third normalised from (3NF)

The requirements that a relation should satisfy to be in 3NF:
- No multivalued attributes, i.e. it MUST BE in 1NF
(Remember: Every cell must contain a single value!)

AND

- No partial dependencies (every non-key attribute must be fully functionally
dependent on the ENTIRE primary key), i.e. it MUST BE in 2NF

AND

- No transitive dependencies (no functional dependencies on non-primary-key
attributes)

### Transitive dependency

Transitive dependency is a dependency of non-key attributes on another non-key attribute.

It is called transitive because the primary key determines an attribute, and this attribute in its
turn determines the third attribute.

### Exercise

FD: full dependency

TD: Transit dependency
Identify transitive dependency in the relation below:
```
students (studentID, studentName, accommodationName, accommodationPrice)
```
Answer: 

PK: studentID, Full dependency studentId -> studentName, studentId -> accommadationName. 

TD: accommadationName -> accommodationPrice

```
modules (modulesCode, acYear, moduleTitle, lectureID, lectureName)
```
Answer: 

Composite PK: modulesCOde, acYear

FD: Composite PK -> lecturerID

PartialD: moduleCode -> moduleTitle

TD: lecturerID -> lecturerName

```
flight(flightNumber, flightDate, pilotID, pilotName, departureTime, arrivalTime, actual_departureTime, actual_arrivalTime)
```
Answer:

Composite PK: flightNumber, flightDate

FD: PK -> pilotId, PK -> departureTime, arrivalTime, actual_departureTime, actual_arrivalTime

TD: pioltID -> pilotName

PD: fligthNumber -> departureTime

### Boyce-Codd Normal Form (BCNF or 3.5NF)

The requirements a relation should satisfy to be in BCNF:

- No multivalued attributes, i.e. it MUST BE in 1NF
(Remember: Every cell must contain a single value!)

AND

- No partial dependencies (every non-key attribute must be fully functionally dependent on the
ENTIRE primary key), i.e. it MUST BE in 2NF

AND

- No transitive dependencies (no functional dependencies on non-primary-key attributes), i.e. it
MUST BE in 3NF

AND

- Every determinant is a Candidate Key, i.e. for each A → B, A is a key or contains a key

In non-BCNF relation there are several overlapping composite candidate keys and a part of one
composite key depends on a non-key attribute. If there is only one candidate key, then 3NF=BCNF

To achieve BCNF, break a non-BCNF relation into two relations in BCNF. 

### Fourth Normal Form (4NF)

4NF = BCNF + NO unrelated multi-valued dependency

### Fifth Normal Form (5NF or Project-Join Normal Form)

5NF = 4NF + NO related multi-valued dependencies

## Denormalisation

What Is Denormalisation?

Denormalisation is a strategy used on a previously-normalized database to increase
performance. The idea behind it is to add redundant data where we think it will help us the
most. We can use extra attributes in an existing table, add new tables, or even create instances
of existing tables. The usual goal is to decrease the running time of select queries by making
data more accessible to the queries or by generating summarized reports in separate tables. This
process can bring some new problems, and we’ll discuss them later.

**A normalised database is the starting point for the denormalisation process. It’s important to
differentiate from the database that has not been normalised and the database that was
normalised first and then denormalised later. The second case is okay; the first is often the
result of bad database design or a lack of knowledge.**

Process opposite to normalisation, where one would add redundancy to a database in order to
improve read performance and optimise queries. During the normalisation process, you
decompose one table into several tables. More tables -more joins, but joins negatively impact
performance.

**Normalisation to prevent anomalies by eliminating redundancy and incompleteness
Denormalisation for performance and query optimisation**

Denormalisation brings the danger of update anomalies and data consistency, therefore the
need for it must be justified and the process of denormalisation thoroughly documented.

### Advantages of denormalisation

The benefits of denormalisation:

1. Improved query performance,

2. Fewer joins,

3. Speed up reporting,

4. Computing commonly-needed values upfront

5. Ability to maintain history information

You don’t need denormalisation if there aren't any performance issues

### Disadvantages of denormalisation

**Extra Disk space:** This is expected, as we’ll have duplicate data.

**Data anomalies:** We have to be very aware of the fact that data now can be changed in more than one place. We must
adjust every piece of duplicate data accordingly. That also applies to computed values and reports. We can achieve this
by using triggers, transactions and/or procedures for all operations that must be completed together.

**Documentation:** We must properly document every denormalisation rule that we have applied. If we modify database
design later, we’ll have to look at all our exceptions and take them into consideration once again. Maybe we don’t need
them anymore because we’ve solved the issue. Or maybe we need to add to existing denormalisation rules. (For
example: We added a new attribute to the client table and we want to store its history value together with everything
we already store. We’ll have to change existing denormalisation rules to achieve that).

**Slowing other operations:** We can expect that we’ll slow down data insert, modification, and deletion operations. If
these operations happen relatively rarely, this could be a benefit. Basically, we would divide one slow select into a larger
number of slower insert/update/delete queries. While a very complex select query technically could noticeably slow
down the entire system, slowing down multiple “smaller” operations should not damage the usability of our application.

**More coding:** Rules 2 and 3 will require additional coding, but at the same time they will simplify some select queries a
lot. If we’re denormalising an existing database we’ll have to modify these select queries to get the benefits of our work.
We’ll also have to update values in newly-added attributes for existing records. This too will require a bit more coding.

