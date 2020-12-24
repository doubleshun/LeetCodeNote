# \#482 License Key Formatting

### Easy:star:

You are given a license key represented as a string S which consists only alphanumeric character and dashes. The string is separated into N+1 groups by N dashes.

Given a number K, we would want to reformat the strings such that each group contains exactly K characters, except for the first group which could be shorter than K, but still must contain at least one character. Furthermore, there must be a dash inserted between two groups and all lowercase letters should be converted to uppercase.

Given a non-empty string S and a number K, format the string according to the rules described above.

> **example:**
>
> Input : S = "5F3Z-2e-9-w" , K = 4
>
> Output : "5F3Z-2E9W"

```text
class Solution:
    def licenseKeyFormatting(self, S: str, K: int) -> str:
        S = S.replace('-','').upper()
        output = ''
        if len(S)%K==0:
            for i in range(0,len(S),K):
                output+=S[i:K+i]
                output+='-'
        else:
            output+=S[:len(S)%K]
            output+='-'
            for i in range(len(S)%K,len(S),K):
                output+=S[i:K+i]
                output+='-'
        return output[:len(output)-1]
```

先取代S中的dashes並將S轉為大寫，判斷S長度是否剛好可以整除K，若非，則output的第一組字串應為S除以K的餘數長度，最後return不傳回最後面的dash

