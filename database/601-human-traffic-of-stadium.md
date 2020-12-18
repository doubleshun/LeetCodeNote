# \#601 Human Traffic of Stadium

### Hard:star::star::star:

Write an SQL query to display the records with three or more rows with **consecutive** `id`'s, and the number of people is greater than or equal to 100 for each. Return the result table ordered by `visit_date` in **ascending order**.

```text
with t as (
select * , id - ROW_NUMBER() OVER(ORDER BY id) AS GroupId from Stadium
where people >= 100 ),
t1 as(
select GroupId,count(GroupId) as CNT from t
group by GroupId)
select id,visit_date,people from t t left join t1 t1 on t.GroupId = t1.GroupId
where CNT>=3
```



