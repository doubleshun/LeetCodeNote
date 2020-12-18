# \#383 Ransom Note

### Easy:star:

Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return true if the ransom note can be constructed from the magazines ; otherwise, it will return false.

Each letter in the magazine string can only be used once in your ransom note.

```text
class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        return  Counter(ransomNote) == (Counter(ransomNote) & Counter(magazine))
```



