# \#118 Pascal's Triangle

### Easy:star:

Given a non-negative integer _numRows_, generate the first _numRows_ of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it.

```text
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:  
        a = 1
        b = 1
        if numRows == 0 :
            return []
        elif numRows == 1 :
            return [[a]]
        elif numRows == 2 :
            return [[a],[a,b]]
        else:
            ans = [[a],[a,b]]
            count = numRows-2 #還要做幾次
            while count > 0 :
                current = []
                tmp  = ans[numRows-count-1]                
                current.append(a)
                for i in range(len(tmp)-1):
                    current.append(tmp[i]+tmp[i+1])
                current.append(b)
                ans.append(current)
                count = count - 1
            return ans
```

