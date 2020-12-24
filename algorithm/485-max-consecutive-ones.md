# \#485 Max Consecutive Ones

### Easy:star:

Given a binary array, find the maximum number of consecutive 1s in this array.

```text
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        max_number = 0
        count = 0
        for i in nums:
            if i == 1 :
                count +=1
            else:
                if count > max_number:
                    max_number = count
                count = 0
        return max(max_number,count)
```

