# \#476 Number Complement

### Easy:star:

 Given a **positive** integer `num`, output its complement number. The complement strategy is to flip the bits of its binary representation.

> **example:**
>
> Input : 5
>
> Output : 2
>
> Explanation : The binary representation of 5 is 101 \( no leading zero bits\), and its complement is 010. So you need to output 2.

```text
class Solution:
    def findComplement(self, num: int) -> int:
        bin_num = list(bin(num)[2:]) #去掉0b
        for idx,val in enumerate(bin_num):
            if val == '0':
                bin_num[idx]='1'
            else:
                bin_num[idx]='0'
        str_complement = ''.join(bin_num)
        return int(str_complement, 2)
```

