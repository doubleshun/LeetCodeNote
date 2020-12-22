# \#461 Hamming Distance

### Easy:star:

The [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance) between two integers is the number of positions at which the corresponding bits are different.

Given two integers `x` and `y`, calculate the Hamming distance.

> **example:**
>
> input: x = 1 , y = 4
>
> output: 2
>
> explanation: x = 1 \( 0001\) , x = 4 \(1000\) at position 1,4 where is corresponding bits are different. Return the number of different positions.

```text
class Solution:
    def hammingDistance(self, x: int, y: int) -> int:
        return bin(x^y).count('1')
```

利用XOR特性，同位置不同值的為1\(因為x,y是十進位，所以x^y會回傳十進位的值，需再將之轉為二進位\)，最後計算有幾個1。

