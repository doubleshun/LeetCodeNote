# \#626 Exchange Seats

### Medium:star::star:

Mary is a teacher in a middle school and she has a table `seat` storing students' names and their corresponding seat ids. The column **id** is continuous increment. Mary wants to change seats for the adjacent students. Can you write a SQL query to output the result for Mary?

```text
with t as (
select s.id , s2.student from seat s left join seat s2 on 
case when s.id % 2 = 1 then s.id+1 else s.id-1 end = s2.id
)
select s.id ,case when t.student is null then s.student else t.student end as student 
from seat s right join t t on s.id = t.id
```





