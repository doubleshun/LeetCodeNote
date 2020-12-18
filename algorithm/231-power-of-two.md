# \#231 Power of Two

### Easy:star:

Given an integer `n`, return _`true` if it is a power of two. Otherwise, return `false`_.

An integer `n` is a power of two, if there exists an integer `x` such that `n == 2**x`

```text
class Solution:
    def isPowerOfTwo(self, n: int) -> bool:
        if n <= 0 :
            return False
        elif n == 1 :
            return True
        else:
            while n > 1 :
                if n % 2 != 0 :
                    return False
                n = n // 2
            return True
```

