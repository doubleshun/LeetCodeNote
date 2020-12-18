# \#1179 Reformat Department Table

### Easy:star:

 Write an SQL query to reformat the table such that there is a department id column and a revenue column **for each month**.

```text
select id , Jan as Jan_Revenue , Feb as Feb_Revenue , Mar as Mar_Revenue , Apr as Apr_Revenue , May as May_Revenue , Jun as Jun_Revenue
, Jul as Jul_Revenue , Aug as Aug_Revenue , Sep as Sep_Revenue , Oct as Oct_Revenue , Nov as Nov_Revenue , Dec as Dec_Revenue
from 
(select * from Department )as d
pivot ( min(d.revenue) for d.month in ([Jan],[Feb],[Mar],[Apr],[May],[Jun],[Jul],[Aug],[Sep],[Oct],[Nov],[Dec])) as p 
```



