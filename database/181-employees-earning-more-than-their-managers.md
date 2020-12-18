# \#181 Employees Earning More Than Their Managers

### Easy:star:

 Given the `Employee` table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.

```text
select Name as Employee from Employee a 
left join (select Id,Salary as ManagerSalary from Employee) b on a.ManagerId = b.Id
where Salary > ManagerSalary
```

