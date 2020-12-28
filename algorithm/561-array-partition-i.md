# \#561 Array Partition I

### Easy:star:

Given an integer array `nums` of `2n` integers, group these integers into `n` pairs `(a1, b1), (a2, b2), ..., (an, bn)` such that the sum of `min(ai, bi)` for all `i` is **maximized**. Return _the maximized sum_.

> **example :** 
>
> Input : nums = \[6,2,6,5,1,2\]
>
> Output : 9
>
> Explanation :  optimal pairing is \(2,1\),\(2,5\),\(6,6\). min\(2,1\)+min\(2,5\)+min\(6,6\) = 9

```text
class Solution:
    def arrayPairSum(self, nums: List[int]) -> int:
        pairs=[]
        max_sum = 0
        nums = sorted(nums)
        for i in range(0,len(nums),2):
            pairs.append([nums[i],nums[i+1]])
        for i in pairs:
            max_sum+=min(i)
        return max_sum
```

將nums由大到小兩兩分堆可得到optimal pairing。\(因為總和要最大，所以由大到小分堆才可以保證總是得到較大的數\)

