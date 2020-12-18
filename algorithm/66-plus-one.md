# \#66 Plus One

### Easy:star:

Given a **non-empty** array of decimal digits representing a non-negative integer, increment one to the integer.

The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.

```text
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        str_digits = ''
        for i in digits :
            str_digits = str_digits + str(i)
        ans = []
        if int(str_digits) == 0:
            digits[-1] = 1
            return digits
        else:
            for i in str(int(str_digits)+1):
                ans.append(i)
            return ans
```

