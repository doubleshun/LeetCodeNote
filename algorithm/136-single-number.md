# \#136 Single Number

### Easy:star:

Given a **non-empty** array of integers `nums`, every element appears _twice_ except for one. Find that single one.

```text
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        """
        My Original Solution :
        
        for i in nums:
            if nums.count(i) == 1 :
                return i
        """
        # perfect solution :  XOR (a⊕0=a , a⊕a=0 )
        a = 0
        for i in nums:
            a ^= i
        return a
```

