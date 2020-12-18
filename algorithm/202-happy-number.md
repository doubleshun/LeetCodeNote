# \#202 Happy Number

### Easy:star:

Write an algorithm to determine if a number `n` is happy.

A **happy number** is a number defined by the following process:

* Starting with any positive integer, replace the number by the sum of the squares of its digits.
* Repeat the process until the number equals 1 \(where it will stay\), or it **loops endlessly in a cycle** which does not include 1.
* Those numbers for which this process **ends in 1** are happy.

Return `true` _if_ `n` _is a happy number, and_ `false` _if not_.

```text
class Solution:
    def isHappy(self, n: int) -> bool:
        sum_of_n = 0
        history = []
        while sum_of_n != 1:
            sum_of_n = 0
            for i in range(len(str(n))):
                sum_of_n += int(str(n)[i])**2  
            if sum_of_n in history: #曾經出現過就跳出迴圈
                break
            else:
                n = sum_of_n
                history.append(sum_of_n)
        return sum_of_n == 1
```

