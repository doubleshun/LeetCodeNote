# \#180 Consecutive Numbers

### Medium:star::star:

Write an SQL query to find all numbers that appear at least three times consecutively.

```text
select distinct l1.Num as ConsecutiveNums from Logs l1 
left join Logs l2 on l1.id = l2.id+1 left join Logs l3 on l1.id = l3.id+2
where l1.Num = l2.Num and l1.Num  = l3.Num
```

