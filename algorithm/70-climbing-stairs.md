# \#70 Climbing Stairs

### Easy:star:

You are climbing a staircase. It takes `n` steps to reach the top.  
Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

```text
class Solution:
    def climbStairs(self, n: int) -> int:
        if n == 1 :
            return 1
        elif n == 2 :
            return 2
        else:
            first = 1
            second = 2 
            for i in range(3,n+1):
                third = first + second
                first = second
                second = third
            return third
```



