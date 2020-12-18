# \#13 Roman to Integer

Given a roman numeral, convert it to an integer.

| Symbol | Value |
| :--- | :--- |
| I | 1 |
| V | 5 |
| X | 10 |
| L | 50 |
| C | 100 |
| D | 500 |
| M | 1000 |

```text
class Solution:
    def romanToInt(self, s: str) -> int:
        dic = {'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000}
        start = 0
        end = 1
        convert_roman = 0
        while start < len(s)-1:
            if dic[s[ start : end ]] < dic[s[start+1:end+1]]:
                convert_roman = convert_roman + dic[s[ start : end ]]*-1
            else:
                convert_roman = convert_roman + dic[s[ start : end ]]
            start = start+1
            end = end+1
        convert_roman = convert_roman + dic[s[ start : end ]]
        return convert_roman
```

