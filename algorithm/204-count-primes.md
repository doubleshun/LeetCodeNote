# \#204 Count Primes

### Easy:star:

 Count the number of prime numbers less than a non-negative number, `n`.

```text
class Solution:
    def countPrimes(self, n: int) -> int:
        # 厄拉托西尼篩法
        is_prime = [True] * n
        for i in range(2, int(n ** 0.5) + 1):
            if  is_prime[i]== True :
                for j in range(i*i,n ,i):
                    is_prime[j] = False
        return is_prime[2:].count(True) 
```

