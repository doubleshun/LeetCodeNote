# \#67 Add Binary

### Easy:star:

 Given two binary strings `a` and `b`, return _their sum as a binary string_.

```text
class Solution:
    def addBinary(self, a: str, b: str) -> str:
        return convert_num_to_binary(convert_binary_to_num(a)+convert_binary_to_num(b))
        
        
def convert_binary_to_num(b):
    num = 0
    for i in range(len(b)) :
        num  = num + int(b[i])*2**(len(b)-i-1)
    return num

def convert_num_to_binary(n):
    if n == 0 :
        return '0'
    else:
        binary = ''
        while n > 0 : 
            binary = binary + str(n%2)
            n = n // 2
        return binary[::-1]
```

