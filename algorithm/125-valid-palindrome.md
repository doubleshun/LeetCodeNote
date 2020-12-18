# \#125 Valid Palindrome

### Easy:star:

Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.

**Note:** For the purpose of this problem, we define empty string as valid palindrome.

```text
class Solution:
    def isPalindrome(self, s: str) -> bool:
        import re
        s = re.sub(r"[^a-z0-9]","",s.lower())
        if s == s[::-1]:
            return True
        else:
            return False
```

