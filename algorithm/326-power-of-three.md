# \#326 Power of Three

### Easy:star:

Given an integer `n`, return _`true` if it is a power of three. Otherwise, return `false`_.

An integer `n` is a power of three, if there exists an integer `x` such that `n == 3**x`.

```text
class Solution:
    def isPowerOfThree(self, n: int) -> bool:
        if n <= 0 :
            return False
        while n > 1 :
            if n % 3 == 0:
                n = n // 3
            else :
                return False
        return True
```

