# \#506 Relative Ranks

### Easy :star:

Given scores of **N** athletes, find their relative ranks and the people with the top three highest scores, who will be awarded medals: "Gold Medal", "Silver Medal" and "Bronze Medal".

> **example:**
>
> Input : \[10,3,8,9,4\]
>
> Output : \["Gold Medal","5","Bronze Medal","Silver Medal","4"\]

```text
class Solution:
    def findRelativeRanks(self, nums: List[int]) -> List[str]:
        sorted_num = sorted(nums)
        rank = len(nums)
        dict_num = {}
        for i in sorted_num:
            if rank == 1 :
                dict_num[i] = 'Gold Medal'
            elif rank == 2 :
                dict_num[i] = 'Silver Medal'
            elif rank == 3 :
                dict_num[i] = 'Bronze Medal'
            else:
                dict_num[i] = str(rank)
            rank-=1
        return list(map(dict_num.get,nums))
```

先排序好nums，將nums的值與其對應的排名存成dictionary，最後再用對應的方式產出排名。

