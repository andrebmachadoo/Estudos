# Get number before and after id

```sql
SELECT * FROM tablename WHERE id = 2 
OR id = (
    SELECT MAX(id) FROM tablename WHERE id < 2
) 
OR id = (
    SELECT MIN(id) FROM tablename WHERE id > 2
);


SELECT
    id,
    (SELECT MAX(id) FROM tablename WHERE id < p.id) AS maior,
    (SELECT MIN(id) FROM tablename WHERE id > p.id) AS menor
FROM
    tablename p
HAVING id = 2 OR id = maior OR id = menor
``` 

_By Andre_