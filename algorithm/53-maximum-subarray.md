# \#53 Maximum Subarray

### Easy:star:

 Given an integer array `nums`, find the contiguous subarray \(containing at least one number\) which has the largest sum and return _its sum_.

```text
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        sums = 0
        maximum = min(nums)
        for i in nums:
            sums = sums+i                            
            if i>sums:
                sums = i
            if sums>maximum:
                maximum = sums
        return maximum
```



