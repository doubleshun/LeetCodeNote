---
description: >-
  Write a SQL query for a report that provides the following information for
  each person in the Person table, regardless if there is an address for each of
  those people:[FirstName, LastName, City, Stat]
---

# \#175 Combine Two Tables

```text
select FirstName, LastName, City, State from Person a left join 
Address b on a.PersonId = b.PersonId
```

