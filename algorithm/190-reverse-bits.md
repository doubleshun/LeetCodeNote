# \#190 Reverse Bits

### Easy:star:

Reverse bits of a given 32 bits unsigned integer.

```text
class Solution:
    def reverseBits(self, n: int) -> int:
        n = '{:032b}'.format(n) #convert integer to bin32
        str_reverseBits = n[::-1]
        return int(str_reverseBits,2)
```

