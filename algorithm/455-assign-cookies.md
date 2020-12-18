# \#455 Assign Cookies

### Easy:star:

Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child `i` has a greed factor `g[i]`, which is the minimum size of a cookie that the child will be content with; and each cookie `j` has a size `s[j]`. If `s[j] >= g[i]`, we can assign the cookie `j` to the child `i`, and the child `i` will be content. Your goal is to maximize the number of your content children and output the maximum number.

```text
class Solution:
    def findContentChildren(self, g: List[int], s: List[int]) -> int:
        count_child = 0 
        g = sorted(g , reverse = True)
        other_g = []
        for i in range(len(g)):
            if g[i] in s :
                count_child+=1
                s.remove(g[i])
            else:
                other_g.append(g[i])
        s = sorted(s , reverse = True )
        for j in other_g:
            for i in s:
                if i >= j:
                    count_child+=1
                    s.remove(i)
                    break
            
        return count_child
```

