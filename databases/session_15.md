# Mongo db

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766731-dt-content-rid-12022236_2/courses/1819-CM6211/session%2015%20-%20MongoDB%281%29.pdf)

MongoDB stores BSON documents (data records) in collections.

MongoDB stores collections in databases.

### Documents

A record in a MongoDB collection and the basic unit of data in MongoDB. Documents are
analogous to JSON objects but exist in the database in a more type-rich format known as BSON.
MongoDB documents are composed of field-and-value pairs.
The value of a field can be any of the BSON data types, including other documents, arrays, and
arrays of documents.

### Collection

A grouping of MongoDB documents. A collection is the equivalent of an RDBMS table. A
collection exists within a single database. Collections do not enforce a schema. Documents
within a collection can have different fields. Typically, all documents in a collection have a similar
or related purpose.

## Modeling cardinality important for exam
