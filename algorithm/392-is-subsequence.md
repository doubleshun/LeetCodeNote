# \#392 Is Subsequence

### Easy:star:

Given a string **s** and a string **t**, check if **s** is subsequence of **t**.

A subsequence of a string is a new string which is formed from the original string by deleting some \(can be none\) of the characters without disturbing the relative positions of the remaining characters. \(ie, `"ace"` is a subsequence of `"abcde"` while `"aec"` is not\).

```text
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        pointer_t = 0
        is_sub = True
        for j in range(len(s)):
            if pointer_t >= len(t) or is_sub == False :
                is_sub = False
                break
            else:
                for i in range(pointer_t,len(t)):
                    if t[i] == s[j]:
                        pointer_t=i+1
                        is_sub = True
                        break
                    else:
                        is_sub = False
        return is_sub
        
            
```

