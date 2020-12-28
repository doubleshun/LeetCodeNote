# \#496 Next Greater Element I

### Easy:star:

You are given two arrays **\(without duplicates\)** `nums1` and `nums2` where `nums1`’s elements are subset of `nums2`. Find all the next greater numbers for `nums1`'s elements in the corresponding places of `nums2`.

The Next Greater Number of a number **x** in `nums1` is the first greater number to its right in `nums2`. If it does not exist, output -1 for this number.

```text
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        ans = []
        for i in nums1:
            found = False
            for j in nums2[nums2.index(i):]:
                if j>i:
                    ans.append(j)
                    found = True
                    break
            if found == False:
                ans.append(-1)
        return ans
```

對每一個在nums1的value i ，i在nums2的位置右邊是否有比i大的數，若否則表示-1  
ex : nums1 = \[4,1,2\] nums2 = \[1,3,4,2\]  
4 : nums2的4右邊沒有比4大的數 --&gt; -1  
1 : nums2的1右邊第一個比1大的數是3 --&gt; 3  
2 : nums2的2右邊沒有比2大的數 --&gt; -1  
==&gt; output : \[-1,3,-1\]

