# \#9 Palindrome Number

### Easy:star:

Determine whether an integer is a palindrome. An integer is a palindrome when it reads the same backward as forward.

**Follow up:** Could you solve it without converting the integer to a string?

```text
class Solution:
    def isPalindrome(self, x: int) -> bool:
        if x > 2**31-1 or x < -2**31 :
            return False
        else:
            if x < 0 :
                return False
            else:
                a = []
                while x//10 > 0 :
                    a.append(x%10)
                    x = x//10
                a.append(x)
                for i in range(len(a)//2):
                    if a[i] != a[len(a)-1-i]:
                        return False
                return True
```

