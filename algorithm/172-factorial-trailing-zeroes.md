# \#172 Factorial Trailing Zeroes

### Easy:star:

 Given an integer `n`, return _the number of trailing zeroes in `n!`_.

```text
class Solution:
    def trailingZeroes(self, n: int) -> int:
        if n == 0 :
            return 0
        else:
            str_fact = str(Factorial(n))
            count = 0
            found = True
            while found == True :
                if str_fact[-1-count] == '0' :
                    count += 1
                else:
                    found = False
            return count
    
def Factorial(n):
    if n ==1 :
        return 1
    else:
        return n*Factorial(n-1)
```



