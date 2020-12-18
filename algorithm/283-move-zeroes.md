# \#283 Move Zeroes

### Easy:star:

 Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

```text
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        count = 1
        idx = 0
        while count <= len(nums) :
            if nums[idx] == 0 :
                nums.pop(idx)
                nums.append(0)
                count += 1
            else:
                idx = idx+1
                count += 1
```



