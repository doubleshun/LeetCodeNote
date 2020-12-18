# \#14 Longest Common Prefix

### Easy:star:

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

```text
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if len(strs) == 0 :
            return ""
        elif len(strs) == 1 :
            return strs[0] 
        else:
            Need_compare = True
            index = 0
            common_str = ""
            while (index < len(strs[0])) & (Need_compare == True):
                compare = strs[0][index]
                tag = True
                for i in strs:
                    if index > len(i)-1:
                        tag = False
                        break
                    else:
                        if i[index] != compare:
                            tag = False
                            break
                if tag == True:
                    common_str = common_str + compare
                    index = index+1
                else:
                    Need_compare = False
            return common_str
```



