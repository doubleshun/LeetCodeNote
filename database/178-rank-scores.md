# \#178 Rank Scores

### Medium:star::star:

Write a SQL query to rank scores. If there is a tie between two scores, both should have the same ranking. Note that after a tie, the next ranking number should be the next consecutive integer value. In other words, there should be no "holes" between ranks.

```text
select score , dense_rank() over (order by score desc) as Rank from Scores
```



