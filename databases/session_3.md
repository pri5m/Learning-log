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

Identify transitive dependency in the relation below:
```
students (studentID, studentName, accommodationName, accommodationPrice)
```
Answer: 

```
modules (modulesCode, acYear, moduleTitle, lectureID, lectureName)
```

```
flight(flightNumber, flightDate, pilotID, pilotName, departureTime, arrivalTime, actual_departureTime, actual_arrivalTime)
```
