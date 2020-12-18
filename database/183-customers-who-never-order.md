# \#183 Customers Who Never Order

### Easy:star:

 Suppose that a website contains two tables, the `Customers` table and the `Orders` table. Write a SQL query to find all customers who never order anything.

```text
select Name as Customers from Customers a left join Orders b on a.Id = b.CustomerId
where CustomerId is null
```

