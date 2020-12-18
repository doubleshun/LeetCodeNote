# \#7 Reverse Integer

### Easy:star:

Given a 32-bit signed integer, reverse digits of an integer.

```text
class Solution:
    def reverse(self, x: int) -> int:
        if x > 2**31-1 or x < -2**31 :
            return 0
        else:
            if x<0 :
                x = x*(-1)
                reverse = 0
                while x // 10 > 0 :
                    reverse = 10*reverse + x%10
                    x = x // 10
                reverse = (10*reverse + x) * -1
                if reverse > 2**31-1 or reverse < -2**31 :
                    return 0
                else:
                    return reverse
            else :
                reverse = 0
                while x // 10 > 0 :
                    reverse = 10*reverse + x%10
                    x = x // 10
                reverse = (10*reverse + x)
                if reverse > 2**31-1 or reverse < -2**31 :
                    return 0
                else:
                    return reverse
```

