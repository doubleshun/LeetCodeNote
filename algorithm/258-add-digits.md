# \#258 Add Digits

### Easy :star:

 Given a non-negative integer `num`, repeatedly add all its digits until the result has only one digit.

```text
class Solution:
    def addDigits(self, num: int) -> int:
        while num >= 0 :
            s = list(str(num))
            s = list(map(int,s))
            if sum(s) < 10 :
                return sum(s)
            else :
                num = sum(s)
```

