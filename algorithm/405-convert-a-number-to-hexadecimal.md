# \#405 Convert a Number to Hexadecimal

### Easy:star:

Given an integer, write an algorithm to convert it to hexadecimal. For negative integer, [two’s complement](https://en.wikipedia.org/wiki/Two%27s_complement) method is used.

**Note:**

1. All letters in hexadecimal \(`a-f`\) must be in lowercase.
2. The hexadecimal string must not contain extra leading `0`s. If the number is zero, it is represented by a single zero character `'0'`; otherwise, the first character in the hexadecimal string will not be the zero character.
3. The given number is guaranteed to fit within the range of a 32-bit signed integer.
4. You **must not use any method provided by the library** which converts/formats the number to hex directly.

```text
class Solution:
    def toHex(self, num: int) -> str:
        dict_lessthan10 = {'0000':'0','0001':'1','0010':'2','0011':'3','0100':'4','0101':'5','0110':'6','0111':'7','1000':'8','1001':'9'}
        dict_greaterthan10 = {'1010':'a','1011':'b','1100':'c','1101':'d','1110':'e','1111':'f'}
        list_hex = []
        if num < 0 :
            num += 2**32
        elif num == 0 :
            return '0'
        while num > 0 :
            list_hex.append(str(num%2))
            num = num//2
        str_hex = ''.join(list_hex)
        str_hex = str_hex[::-1]
        str_hex = str_hex.zfill(32)
        ans = ''
        start = 0
        end = 4
        while end <= len(str_hex):
            if str_hex[start:end] in dict_greaterthan10.keys():
                ans += dict_greaterthan10[str_hex[start:end]]
            else :
                ans += dict_lessthan10[str_hex[start:end]]
            start = end
            end += 4
        return ans.lstrip('0')
```

