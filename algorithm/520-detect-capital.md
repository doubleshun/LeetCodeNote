# \#520 Detect Capital

### Easy:star:

Given a word, you need to judge whether the usage of capitals in it is right or not.

We define the usage of capitals in a word to be right when one of the following cases holds:

1. All letters in this word are capitals, like "USA".
2. All letters in this word are not capitals, like "leetcode".
3. Only the first letter in this word is capital, like "Google".

Otherwise, we define that this word doesn't use capitals in a right way.

```text
class Solution:
    def detectCapitalUse(self, word: str) -> bool:
        if word.isupper(): #1.全部都大寫
            return True
        elif word.islower(): #2.全部都小寫
            return True
        elif word[0].isupper() and word[1:].islower(): #3.只有第一個字大寫，其他小寫
            return True
        else:
            return False
```

