# \#290 Word Pattern

### Easy:star:

Given a `pattern` and a string `s`, find if `s` follows the same pattern.

Here **follow** means a full match, such that there is a bijection between a letter in `pattern` and a **non-empty** word in `s`.

```text
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        d = {}
        list_s = s.split(' ')
        if len(pattern) != len(list_s) :
            return False
        else:
            for idx,value in enumerate(pattern) :
                if value not in d.keys():
                    if list_s[idx] not in d.values():
                        d[value] = list_s[idx]
                    else:
                        return False
                else:
                    if d[value] != list_s[idx]:
                        return False
            return True
```



