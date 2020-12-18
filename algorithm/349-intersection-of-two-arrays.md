# \#349 Intersection of Two Arrays

### Easy:star:

Given two arrays, write a function to compute their intersection.

```text
class Solution:
    def intersection(self, nums1: List[int], nums2: List[int]) -> List[int]:
        set1 = set(nums1)
        set2 = set(nums2)
        return set1.intersection(set2)
```

