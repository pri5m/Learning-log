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
  `jobID` INTEGER NOT NULL,  # use comma even on the last line
);  #Don't forget the semi colon here
```
