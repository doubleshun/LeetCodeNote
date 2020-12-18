# \#242 Valid Anagram

### Easy:star:

 Given two strings _s_ and _t_ , write a function to determine if _t_ is an anagram of _s_.

```text
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        dict_s , dict_t = {} , {}
        dict_s.fromkeys(set(s))
        dict_t.fromkeys(set(t))
        for i in set(s):
            dict_s[i] = s.count(i)
        for i in set(t):
            dict_t[i] = t.count(i)
        return dict_s == dict_t
```

