# \#507 Perfect Number

### Easy:star:

A [**perfect number**](https://en.wikipedia.org/wiki/Perfect_number) is a **positive integer** that is equal to the sum of its **positive divisors**, excluding the number itself. A **divisor** of an integer `x` is an integer that can divide `x` evenly.

Given an integer `n`, return `true` _if_ `n` _is a perfect number, otherwise return_ `false`.

> **example:**
>
> Input : num = 28
>
> Ouptut : True
>
> Explanation : 28 = 1+2+4+7+14 \( 1,2,4,7,14 are all divisors of 28\)

```text
class Solution:
    def checkPerfectNumber(self, num: int) -> bool:
        if num == 1 :
            return False
        else:
            divisor = []
            for i in range(1,int(num**0.5)+1):
                if num % i == 0 :
                    divisor.append(i)
                    divisor.append(num//i)
            if (sum(divisor)-num) == num :
                return True
            else:
                return False
```

由於時間複雜度的關係，所以for 只跑1 到 num的開根號，每次將商數與被除數加入因數的List，因為當因數是1的時候，會把num本身這個因數也加進List，所以再算sum的時候要扣掉。

