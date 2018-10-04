# Database normalisation

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

