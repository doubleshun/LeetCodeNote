# \#463 Island Perimeter

### Easy:star:

You are given `row x col` `grid` representing a map where `grid[i][j] = 1` represents land and `grid[i][j] = 0` represents water.

Grid cells are connected **horizontally/vertically** \(not diagonally\). The `grid` is completely surrounded by water, and there is exactly one island \(i.e., one or more connected land cells\).

The island doesn't have "lakes", meaning the water inside isn't connected to the water around the island. One cell is a square with side length 1. The grid is rectangular, width and height don't exceed 100. Determine the perimeter of the island.

![](../.gitbook/assets/island.png)

> **example:**
>
> Input : grid = \[\[0,1,0,0\],\[1,1,1,0\],\[0,1,0,0\],\[1,1,0,0\]\]
>
> Output : 16

```text
class Solution:
    def islandPerimeter(self, grid: List[List[int]]) -> int:
        total_square = 0
        adjacent_side = 0
        for i in range(len(grid)):
            for j in range(len(grid[i])):
                if grid[i][j] == 1:
                    total_square+=1
                    if i !=len(grid)-1:#比下面
                        if grid[i+1][j]==1 : 
                            adjacent_side+=1
                    if j!=len(grid[i])-1:#比右邊
                        if grid[i][j+1] == 1 : 
                            adjacent_side+=1
        return total_square*4-adjacent_side*2
```

計算有幾個陸地\(一個陸地有4個邊\)，再扣掉陸地相鄰的邊\(相鄰的陸地交會共2個邊\)，即為陸地周長。以右邊或下面有陸地為相鄰基準\(就不會重複計算到了\)，最右方及最下方的陸地不會再有相鄰陸地故不需計算。

