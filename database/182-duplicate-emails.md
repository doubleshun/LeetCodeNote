# \#182 Duplicate Emails

### Easy:star:

 Write a SQL query to find all duplicate emails in a table named `Person`.

```text
select Email from (select Email,count(Email) CNT from Person group by Email) as NewPerson
where CNT > 1
```

