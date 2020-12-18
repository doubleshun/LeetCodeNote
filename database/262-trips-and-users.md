# \#262 Trips and Users

### Hard:star::star::star:

 Write a SQL query to find the cancellation rate of requests made by unbanned users \(both client and driver must be unbanned\) between **Oct 1, 2013** and **Oct 3, 2013**. The cancellation rate is computed by dividing the number of canceled \(by client or driver\) requests made by unbanned users by the total number of requests made by unbanned users.

```text
with t as (
select Status,Request_at from Trips t left join Users u on t.Client_id = u.Users_Id left join Users u2 on t.Driver_Id = u2.Users_Id
where u.Banned = 'No' and u2.Banned = 'No'
),t1 as (
select Request_at , count(Request_at) as num_cancell from t
where Status != 'completed'
group by Request_at)
,t2 as (
select Request_at , count(Request_at) as num_all from t
group by Request_at)
select t2.Request_at as [Day] , cast(round(isnull(num_cancell,0)*1.00/num_all,2) as float) as  [Cancellation Rate]  from t1 right join t2 on t1.Request_at = t2.Request_at
where t2.Request_at between '2013-10-01' and'2013-10-03'
```

