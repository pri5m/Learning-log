# Schema Change Management and Database Migrations

[Slides](https://learningcentral.cf.ac.uk/bbcswebdav/pid-4766727-dt-content-rid-11989835_2/courses/1819-CM6211/Week%205%20-%20Session%2012%20%20-%20%20Schema%20Change%20Management%20and%20Database%20Migrations.pdf)

## Best practice of change management

1. Work only on a local copy of the database (not on a production database) and
propagate changes via versioned change scripts

2. Explicit database version number

3. Each change creates a new (sub)version of the database

4. Code is aware of what schema it expects to work against (e.g. by committing the
actual DDL script)

5. Keep the script for every version (use mysqldump utility)

6. You should be able to revert any change, if needed (write a rollback script for every
change script!)

7. Track changes in a special table within your schema

8. Always test each database change locally against a variety of test data, and test your
code with it, only then commit the change script into source control.

9. Once a DDL script is published into source control, do not change it.

10. Do not run the same change script more than once.

11. Always backup a production database before applying a change script. If a change
script happens to fail with an error, you can at least get the database back into a
known state.

12. Maintain separate changelog for Stored Procedures.

## Chnage the schema of this database into a normalised one

```
DROP SCHEMA IF EXISTS uni;

CREATE SCHEMA uni;

USE uni;

CREATE TABLE modulesOriginal 
(
  moduleCode int NOT NULL PRIMARY KEY,
  moduleTitle char(255) NOT NULL,
  startDate date NULL DEFAULT '2016-10-01',
  endDate date NULL DEFAULT '2017-01-21',
  credit smallint NOT NULL,
  lecturerID int NOT NULL,
  lecturerName varchar(50) NOT NULL,
  lecturerSurname varchar(50)
);

CREATE TABLE modules
( 
  moduleCode int NOT NULL PRIMARY KEY,
  moduleTitle char(255) NOT NULL,
  startDate date NULL DEFAULT '2016-10-01',
  endDate date NULL DEFAULT '2017-01-21',
  credit smallint NOT NULL,
  lecturerID int NOT NULL
);

CREATE TABLE lecturers
(
  lecturerID int NOT NULL,
  lecturerName varchar(50) NOT NULL,
  lecturerSurname varchar(50)
);


INSERT INTO modulesOriginal
(`moduleCode`,
`moduleTitle`,
`startDate`,
`endDate`,
`credit`,
`lecturerID`,
`lecturerName`,
`lecturerSurname`)
VALUES
(111,
'Databases',
'2016-10-01',
'2017-01-21',
20,
1,
'Nia',
'Williams');


INSERT INTO modulesOriginal
(`moduleCode`,
`moduleTitle`,
`startDate`,
`endDate`,
`credit`,
`lecturerID`,
`lecturerName`,
`lecturerSurname`)
VALUES
(222,
'Emerging Tech',
'2016-10-01',
'2017-01-21',
20,
2,
'Ian',
'Smith');


INSERT INTO modulesOriginal
(`moduleCode`,
`moduleTitle`,
`startDate`,
`endDate`,
`credit`,
`lecturerID`,
`lecturerName`,
`lecturerSurname`)
VALUES
(333,
'Databases',
'2016-10-01',
'2017-01-21',
20,
3,
'Mark',
'Johns');

INSERT INTO modulesOriginal
(`moduleCode`,
`moduleTitle`,
`startDate`,
`endDate`,
`credit`,
`lecturerID`,
`lecturerName`,
`lecturerSurname`)
VALUES
(444,
'Java',
'2016-10-01',
'2017-01-21',
10,
4,
'Ellie',
'Marks');


INSERT INTO modulesOriginal
(`moduleCode`,
`moduleTitle`,
`startDate`,
`endDate`,
`credit`,
`lecturerID`,
`lecturerName`,
`lecturerSurname`)
VALUES
(555,
'Agile',
'2016-10-01',
'2017-01-21',
20,
5,
'Rob',
'Evans');

SELECT * FROM modulesOriginal;


CREATE TABLE IF NOT EXISTS db_versions
(
db_version varchar(5),
active boolean,
description text,
PRIMARY KEY (db_version) 
);

INSERT INTO db_versions VALUES ('0.1', TRUE, 'Unnormalised schema (UNF)');


-- CREATE a stored proceudre that returns the version of the database
DROP procedure IF EXISTS `find_db_version`;

DELIMITER $$

CREATE PROCEDURE find_db_version ()
BEGIN

SELECT db_version FROM db_versions WHERE active=TRUE;

END$$

DELIMITER ;

CALL find_db_version (); -- shows the version of the DB you work with 
-- (given that the data in the table db_verisons is up to date)

INSERT INTO modules(moduleCode, moduleTitle, startDate, endDate, credit, lecturerID)
SELECT moduleCode, moduleTitle, startDate, endDate, credit, lecturerID
FROM modulesoriginal;

INSERT INTO lecturers(lecturerID, lecturerName, lecturerSurname)
SELECT lecturerID, lecturerName, lecturerSurname
FROM modulesoriginal;
```

Transfer the data from moduklesoriginal into two new normalised tables, lecturers and modules using INSERT INTO
