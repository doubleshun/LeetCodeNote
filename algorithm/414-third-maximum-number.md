# \#414 Third Maximum Number

### Easy:star:

Given a **non-empty** array of integers, return the **third** maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O\(n\).

```text
class Solution:
    def thirdMax(self, nums: List[int]) -> int:
        a = sorted(list(set(nums)),reverse=True)
        if len(a) < 3 :
            return max(a)
        else:
            return a[2]
```





