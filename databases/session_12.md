
# Best practice of change management

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

