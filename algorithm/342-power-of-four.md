# \#342 Power of Four

### Easy:star:

Given an integer `n`, return _`true` if it is a power of four. Otherwise, return `false`_.

An integer `n` is a power of four, if there exists an integer `x` such that `n == 4**x`.

```text
class Solution:
    def isPowerOfFour(self, n: int) -> bool:
        if n <= 0 :
            return False
        while n > 1 :
            if n % 4 == 0:
                n = n // 4
            else :
                return False
        return True        
```

