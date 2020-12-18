# \#345 Reverse Vowels of a String

### Easy:star:

Write a function that takes a string as input and reverse only the vowels of a string.

```text
class Solution:
    def reverseVowels(self, s: str) -> str:
        vowels = ['a', 'e', 'i',  'o',  'u', 'A', 'E', 'I', 'O', 'U'] #母音
        list_vowels = []

        list_s = []
        list_s[:0] = s

        for idx,value in enumerate(list_s):
            if value in vowels:
                list_vowels.append(value)
                list_s[idx] = "-1"
        for idx,value in enumerate(list_s):
            if value == "-1":
                list_s[idx] = list_vowels.pop()

        t = ''
        t = t.join(list_s)
        return t
```

