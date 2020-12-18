# \#168 Excel Sheet Column Title

### Easy:star:

Given a positive integer, return its corresponding column title as appear in an Excel sheet.

> **example :** 
>
> * 1 -&gt; A
> * 2 -&gt; B
> * 3 -&gt; C
> * ....
> * 26 -&gt; Z
> * 27 -&gt; AA
> * 28 -&gt; AB
> * ...

```text
class Solution:
    def convertToTitle(self, n: int) -> str:
        import string
        list_title = list(string.ascii_uppercase)
        Quotient = (n-1) // 26 #商數
        remainder = (n-1) % 26 #餘數
        if Quotient == 0 :
            return list_title[remainder]
        else:
            str_title = ''
            while Quotient > 26 :
                remainder_of_Q = (Quotient-1)%26
                Quotient = (Quotient-1)//26
                str_title += list_title[remainder_of_Q]
            str_title += list_title[Quotient-1]
            str_title = str_title[::-1]
            str_title += list_title[remainder]
            return str_title
```

