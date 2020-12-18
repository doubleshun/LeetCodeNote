# \#263 Ugly Number

### Easy:star:

Write a program to check whether a given number is an ugly number.

Ugly numbers are **positive numbers** whose prime factors only include `2, 3, 5`.

```text
class Solution:
    def isUgly(self, num: int) -> bool:
        if num<=0:
            return False
        elif num ==1 or num ==2 or num == 3 or num ==5 :
            return True
        else:
            while num > 1:
                if num % 2 == 0 :
                    num = num // 2 
                elif num % 3 == 0 :
                    num = num // 3
                elif num % 5 == 0 :
                    num = num // 5
                else:
                    return False
            return True
```

