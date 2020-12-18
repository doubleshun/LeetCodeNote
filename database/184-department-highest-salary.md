# \#184 Department Highest Salary

### Medium :star::star:

Write a SQL query to find employees who have the highest salary in each of the departments. For the above tables, your SQL query should return the following rows \(order of rows does not matter\).

```text
with t as (
select * , DENSE_RANK() over (partition by Department order by Salary desc) as d_rank from 
(
select e.Name as Employee , Salary , d.Name as Department from Employee e inner join Department d on e.DepartmentId = d.Id
) AS A
)
select Department , Employee , Salary from t 
where d_rank = 1
```

