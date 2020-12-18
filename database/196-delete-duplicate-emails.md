# \#196 Delete Duplicate Emails

### Easy:star:

 Write a SQL query to **delete** all duplicate email entries in a table named `Person`, keeping only unique emails based on its smallest **Id**.

```text
DELETE FROM Person 
WHERE Id NOT IN (select a.minID from (SELECT MIN(Id) as minID FROM Person GROUP BY Email)a)
```



