# \#20 Valid Parentheses

### Easy:star:

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

```text
class Solution:
    def isValid(self, s: str) -> bool:
        stack = []
        for i in range(len(s)):
            if s[i] == '(' or s[i] == '{' or s[i] == '[' :
                stack.append(s[i])
            elif s[i] == ')':
                if len(stack) == 0 or stack.pop() != '(':
                    return False
            elif s[i] == '}':
                if len(stack) == 0 or stack.pop() != '{':
                    return False
            elif s[i] == ']':
                if len(stack) == 0 or stack.pop() != '[':
                    return False
        if len(stack)>0:
            return False
        else:
            return True
```

