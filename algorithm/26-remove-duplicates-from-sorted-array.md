# \#26 Remove Duplicates from Sorted Array

### Easy:star:

Given a sorted array _nums_, remove the duplicates [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) such that each element appears only _once_ and returns the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) with O\(1\) extra memory.

```text
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        i = 0
        while i < len(nums)-1: 
            if nums[i] == nums[i+1]:
                nums.remove(nums[i])
            else:
                i = i+1
        return len(nums)
```



