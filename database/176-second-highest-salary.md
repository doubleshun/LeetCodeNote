# \#176 Second Highest Salary

 Write a SQL query to get the second highest salary from the `Employee` table.

```text
select max(Salary) as SecondHighestSalary  from Employee
where Salary not in (select max(Salary) from Employee)
```

