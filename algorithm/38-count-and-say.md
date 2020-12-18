# \#38 Count and Say

### Easy:star:

The **count-and-say** sequence is a sequence of digit strings defined by the recursive formula:

* `countAndSay(1) = "1"ne`
* `countAndSay(n)` is the way you would "say" the digit string from `countAndSay(n-1)`, which is then converted into a different digit string.

> example :
>
> Input : n = 4
>
> Output : "1211"
>
> Explanation : 
>
> * countAndSay\(1\) = "1"
> * countAndSay\(2\) = say "1" = one 1 = "11"
> * countAndSay\(3\) = say "11" = two 1 = "21"
> * countAndSay\(4\) = say"21" = one 2 + one 1 = "12"+"11" = "1211"

```text
class Solution:
    def countAndSay(self, n: int) -> str:
        if n == 1 :
            return '1'
        else :
            n = self.countAndSay(n-1)
            count = 1
            a = []
            if len(str(n)) == 1 :
                return '11'
            else:
                for i in range(1,len(n)) :
                    if n[i] == n[i-1]:
                        if i == len(n)-1 : 
                            a.append(count+1)
                            a.append(n[i])
                        else:
                            count = count+1
                    else :
                        a.append(count)
                        a.append(n[i-1])
                        count = 1
                        if i == len(n)-1 : 
                            a.append(count)
                            a.append(n[i])
            ans = ''
            for i in range(len(a)):
                ans = ans + str(a[i])
            return ans
```

