## Temporary table

> This document is help for you create a temporary table in database mysql:

```sql
# Create table
CREATE TEMPORARY TABLE tablename(
	id INT,
	field1 VARCHAR(20)
) ENGINE = MEMORY;

#Input values
INSERT INTO tablename (id,field1) VALUES (1,'field test type varchar');
INSERT INTO tablename (id,field1) VALUES (2,'field test type varchar');
INSERT INTO tablename (id,field1) VALUES (3,'field test type varchar');

#List values
SELECT * FROM tablename;

#Drop table
DROP TABLE IF EXISTS tablename;
```

___By Andre Machado___