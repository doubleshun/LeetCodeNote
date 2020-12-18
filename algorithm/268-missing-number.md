# \#268 Missing Number

### Easy:star:

 Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return _the only number in the range that is missing from the array._

```text
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        for i in range(0,len(nums)+1):
            if i not in nums:
                return i
```



