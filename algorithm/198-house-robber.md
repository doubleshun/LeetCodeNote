# \#198 House Robber

### Medium:star::star:

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and **it will automatically contact the police if two adjacent houses were broken into on the same night**.

```text
class Solution:
    def rob(self, nums: List[int]) -> int:
        solved = [0] * len(nums)
        if len(nums) == 0 :
            return 0
        elif len(nums) == 1 :
            return nums[0]
        elif len(nums) == 2 :
            return max(nums)
        elif len(nums) == 3 :
            return max(nums[1],nums[0]+nums[2])
        else:
            solved[0] = nums[0]
            solved[1] = max(nums[0],nums[1])
            solved[2] = max(nums[1],nums[0]+nums[2])
            for i in range(3,len(nums)):
                solved[i] = max(solved[i-2],solved[i-3])+nums[i]
            return max(solved)
```

