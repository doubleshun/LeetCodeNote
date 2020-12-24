# \#492 Construct the Rectangle

### Easy:star:

A web developer needs to know how to design a web page's size. So, given a specific rectangular web page’s area, your job by now is to design a rectangular web page, whose length L and width W satisfy the following requirements:

1. The area of the rectangular web page you designed must equal to the given target area.
2. The width `W` should not be larger than the length `L`, which means `L >= W`.
3. The difference between length `L` and width `W` should be as small as possible.

Return _an array `[L, W]` where `L` and `W` are the length and width of the web page you designed in sequence._

> **example:**
>
> Input : area = 4
>
> Output : \[2,2\]
>
> Explanation : all the possible way is \[1,4\],\[2,2\],\[4,1\] , but it needs L&gt;=M and minimize the difference of L and M , so the answer is \[2,2\]

```text
class Solution:
    def constructRectangle(self, area: int) -> List[int]:
        min_diff = area
        for i in range(int(area**0.5),area+1):
            if area % i == 0 :
                tmp_L = i
                tmp_W = area // i
                if (tmp_L-tmp_W) < min_diff and tmp_L >= tmp_W:
                    min_diff = tmp_L-tmp_W
                    L = tmp_L
                    W = tmp_W
        return [L,W]
```

從area的開根號開始找area的因數，可以減少尋找次數

