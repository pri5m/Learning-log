Just a brief introduction

# What is SQL?

• Structured Query Language
```
INSERT INTO Customers(firstName,surname,phoneNo, employerID )
VALUES ('Ian','Cooper','888888', 1);
```

# What is SQLite3?

• A lightweight DB tool that can stores all info in a simple file.

• Good for light to medium use websites. 

Can create tables in the browser or in atom

The quote marks only matters in the VALUES section, but make sure that the rest of the code has consistent quotes- it just doesn't matter what type: `, ', "

```
CREATE TABLE IF NOT EXISTS 'Orders' (
  `orderID` INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  `customerID` INTEGER NOT NULL,
  `jobID` INTEGER NOT NULL,
);  #Don't forget the semi colon here
```

# garage.sql
```
DROP TABLE IF EXISTS 'Customers';
DROP TABLE IF EXISTS 'Jobs';
DROP TABLE IF EXISTS 'Orders';

CREATE TABLE IF NOT EXISTS 'Customers' (
  `customerID` INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  `firstName` TEXT NOT NULL,
  `surname` TEXT NOT NULL,
  `contactNum` INTEGER NOT NULL,
  `Address` TEXT NOT NULL
);

INSERT INTO `Customers` ('customerID', 'firstName', 'surname', 'contactNum', 'Address') VALUES ('1','Holly', 'Smith', '3423423423', 'Cathays');
INSERT INTO `Customers` ('customerID', 'firstName', 'surname', 'contactNum', 'Address') VALUES ('2','Lauren', 'Heymer', '795983049', 'Newport');

CREATE TABLE IF NOT EXISTS 'Jobs' (
  `jobID` INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  `Job` TEXT NOT NULL,
  `Description` TEXT NOT NULL,
  `Price` INTEGER NOT NULL
);

INSERT INTO `Jobs` ('jobID', 'Job', 'Description', 'Price') VALUES ('1','Oil change', 'Change the oil', '120');
INSERT INTO `Jobs` ('jobID', 'Job', 'Description', 'Price') VALUES ('2','MOT', 'Do the MOT', '299');
INSERT INTO `Jobs` ('jobID', 'Job', 'Description', 'Price') VALUES ('3','Oil and Filter', 'Change the oil and the filter', '199');

CREATE TABLE IF NOT EXISTS 'Orders' (
  `orderID` INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  `customerID` INTEGER NOT NULL,
  `jobID` INTEGER NOT NULL
);

INSERT INTO `Orders` (orderID, customerID, jobID) VALUES (1,23,45);
INSERT INTO `Orders` (orderID, customerID, jobID) VALUES (2,12,16);

```
