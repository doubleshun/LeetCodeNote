# \#191 Number of 1 Bits

### Easy:star:

Write a function that takes an unsigned integer and returns the number of '1' bits it has \(also known as the [Hamming weight](http://en.wikipedia.org/wiki/Hamming_weight)\).

```text
class Solution:
    def hammingWeight(self, n: int) -> int:
        n = '{:032b}'.format(n)
        return n.count('1')
```

