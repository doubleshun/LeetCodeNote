# \#205 Isomorphic Strings

### Easy:star:

Given two strings **s** and **t**, determine if they are isomorphic.

Two strings are isomorphic if the characters in **s** can be replaced to get **t**.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character but a character may map to itself.

```text
class Solution:
    def isIsomorphic(self, s: str, t: str) -> bool:
        d = {}
        for idx,value in enumerate(s) :
            if value not in d.keys():
                if t[idx] not in d.values():
                    d[value] = t[idx]
                else:
                    return False
            else:
                if d[value] != t[idx]:
                    return False
        return True
```

