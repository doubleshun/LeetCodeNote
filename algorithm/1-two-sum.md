---
description: >-
  Given an array of integers nums and an integer target, return indices of the
  two numbers such that they add up to target
---

# \#1 Two Sum

```text
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dic = {}
        for idx,value in enumerate(nums):
            if target - value in dic:
                return [idx,dic[target-value]]
            else:
                dic[value] = idx
```



