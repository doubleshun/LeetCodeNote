# \#387 First Unique Character in a String

### Easy:star:

Given a string, find the first non-repeating character in it and return its index. If it doesn't exist, return -1.

```text
class Solution:
    def firstUniqChar(self, s: str) -> int:
        for key,val in Counter(s).items():
            if val == 1 :
                return s.find(key)
        return -1
```

