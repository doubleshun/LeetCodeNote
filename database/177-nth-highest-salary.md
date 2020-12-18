# \#177 Nth Highest Salary

### Medium:star::star:

 Write a SQL query to get the _n_th highest salary from the `Employee` table.

```text
CREATE FUNCTION getNthHighestSalary(@N INT) RETURNS INT AS
BEGIN
    RETURN (
        /* Write your T-SQL query statement below. */
        select top 1 Salary from 
        (select DENSE_RANK() OVER(order by Salary Desc ) as den_rank , Salary  from Employee) as d
        where  den_rank = @N 
    );
END
```

