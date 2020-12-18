# \#596 Classes More Than 5 Students

### Easy:star:

There is a table `courses` with columns: **student** and **class.** Please list out all classes which have more than or equal to 5 students.

```text
with t as (
select distinct student , class from courses
)
select class from t
group by class
having count(student) >= 5 
```



