# \#119 Pascal's Triangle II

### Easy:star:

Given an integer `rowIndex`, return the `rowIndexth` row of the Pascal's triangle.  
Notice that the row index starts from **0**.

```text
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        return generate(rowIndex+1)[rowIndex]
        
def generate(numRows: int):
    triangle = []

    for row_num in range(numRows):
        # The first and last row elements are always 1.
        row = [None for _ in range(row_num+1)]
        row[0], row[-1] = 1, 1

        # Each triangle element is equal to the sum of the elements
        # above-and-to-the-left and above-and-to-the-right.
        for j in range(1, len(row)-1):
            row[j] = triangle[row_num-1][j-1] + triangle[row_num-1][j]

        triangle.append(row)

    return triangle
```

