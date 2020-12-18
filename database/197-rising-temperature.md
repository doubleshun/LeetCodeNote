# \#197 Rising Temperature

### Easy:star:

 Write an SQL query to find all dates' `id` with higher temperature compared to its previous dates \(yesterday\).

```text
select w2.id from Weather w1 left join Weather w2 on w1.recordDate = DATEADD(day,-1,w2.recordDate) 
where w1.Temperature < w2.Temperature
```



