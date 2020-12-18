# \#27 Remove Element

### Easy:star:

Given an array _nums_ and a value `val`, remove all instances of that value [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) with `O(1)` extra memory.

```text
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        if len(nums) == 0 :
            return len(nums)
        else:
            i = 0
            while i < len(nums) :
                if nums[i] == val:
                    nums.remove(nums[i])
                else:
                    i = i+1
            return len(nums)
```

