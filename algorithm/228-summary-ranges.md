# \#228 Summary Ranges

### Easy:star:

You are given a **sorted unique** integer array `nums`.

Return _the **smallest sorted** list of ranges that **cover all the numbers in the array exactly**_. That is, each element of `nums` is covered by exactly one of the ranges, and there is no integer `x` such that `x` is in one of the ranges but not in `nums`.

Each range `[a,b]` in the list should be output as:

* `"a->b"` if `a != b`
* `"a"` if `a == b`

> **example**:
>
> Input : nums = \[0,1,2,4,5,7\]
>
> Output : \["0-&gt;2","4-&gt;5","7"\]

```text
class Solution:
    def summaryRanges(self, nums: List[int]) -> List[str]:
        if len(nums) == 0:
            return []
        elif len(nums) == 1 :
            return [str(nums[0])]
        else:
            ans = []
            head = nums[0]
            tail = nums[0]
            count = 1
            for i in range(1,len(nums)):
                if head+count != nums[i]:
                    if tail != head :
                        ans.append(str(head)+"->"+str(tail))
                    else:
                        ans.append(str(head))
                    if i == len(nums)-1 :
                        ans.append(str(nums[i]))
                    head = nums[i]
                    tail = nums[i]
                    count = 1
                else:
                    tail = head+count
                    count += 1
                    if i == len(nums)-1 :
                        ans.append(str(head)+"->"+str(tail))
            return ans
```

