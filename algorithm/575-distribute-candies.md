# \#575 Distribute Candies

### Easy:star:

Alice has `n` candies, where the `ith` candy is of type `candyType[i]`. Alice noticed that she started to gain weight, so she visited a doctor.

The doctor advised Alice to only eat `n / 2` of the candies she has \(`n` is always even\). Alice likes her candies very much, and she wants to eat the maximum number of different types of candies while still following the doctor's advice.

Given the integer array `candyType` of length `n`, return _the **maximum** number of different types of candies she can eat if she only eats_ `n / 2` _of them_.

> **example:**
>
> Input : candyType = \[1,1,2,2,3,3\]
>
> Output : 3
>
> Explanation : Alice can only eat 6 / 2 = 3 candies. Since there are only 3 types, she can eat one of each type.

```text
class Solution:
    def distributeCandies(self, candyType: List[int]) -> int:
        can_eat = len(candyType)//2
        if len(set(candyType)) > can_eat:
            return can_eat
        else:
            return len(set(candyType))
```

如果糖果種類\(ex: 4 types \) &gt; Alice能吃的糖果數\(ex: 3 candies\)，則最多只能選Alice能吃的糖果數\(3\)種糖果類型吃  
相反，如果糖果類型\(ex: 1 type\)&lt;=Alice能吃的糖果數\(ex: 3 candies\)，則最多只能選擇糖果類型\(1\)種糖果吃

