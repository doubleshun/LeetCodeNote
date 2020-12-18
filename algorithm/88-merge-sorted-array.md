# \#88 Merge Sorted Array

### Easy:star:

 Given two sorted integer arrays _nums1_ and _nums2_, merge _nums2_ into _nums1_ as one sorted array.

```text
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        nums3 = sorted(nums1[:m]+nums2[:n])
        for i in range(m+n):
            nums1[i] = nums3[i]
```



