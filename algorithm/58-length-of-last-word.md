# \#58 Length of Last Word

### Easy:star:

Given a string `s` consists of some words separated by spaces, return _the length of the last word in the string. If the last word does not exist, return_ `0`.

A **word** is a maximal substring consisting of non-space characters only.

```text
class Solution:
    def lengthOfLastWord(self, s: str) -> int:
        a = s.split(" ")
        if a[-1] == '' and len(a) == 1:
            return 0
        else:
            for i in range(len(a)-1,-1,-1):
                if a[i] != '':
                    return len(a[i])
            return 0
```

