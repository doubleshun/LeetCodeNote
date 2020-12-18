# \#350 Intersection of Two Arrays II

### Easy:star:

Given two arrays, write a function to compute their intersection.

```text
class Solution:
    def intersect(self, nums1: List[int], nums2: List[int]) -> List[int]:
        list_x = []
        if len(nums1)>=len(nums2):
            for x in nums2:
                if x in nums1:
                    list_x.append(x)
                    nums1.remove(x)
        else:
            for x in nums1:
                if x in nums2:
                    list_x.append(x)
                    nums2.remove(x)
        return list_x
```



