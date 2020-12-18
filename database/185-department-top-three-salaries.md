# \#185 Department Top Three Salaries

### Hard:star::star::star:

Write a SQL query to find employees who earn the top three salaries in each of the department. For the above tables, your SQL query should return the following rows \(order of rows does not matter\).

```text
with t as (
select d.Name as Department , e.Name as Employee , Salary, DENSE_RANK() Over(partition by DepartmentId order by Salary Desc) as d_rank from Employee e inner join Department d on e.DepartmentId = d.Id
)
select Department,Employee,Salary from t
where d_rank <= 3
```

