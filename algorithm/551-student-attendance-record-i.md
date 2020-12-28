# \#551 Student Attendance Record I

### Easy:star:

 You are given a string representing an attendance record for a student. The record only contains the following three characters:

1. **'A'** : Absent.
2. **'L'** : Late.
3. **'P'** : Present.

A student could be rewarded if his attendance record doesn't contain **more than one 'A' \(absent\)** or **more than two continuous 'L' \(late\)**.

You need to return whether the student could be rewarded according to his attendance record.

```text
class Solution:
    def checkRecord(self, s: str) -> bool:
        if Counter(s)['A'] <= 1:
            if 'LLL' in s :
                return False
            else:
                return True
        else:
            return False
```

因為不能超過連續兩個L，所以判斷如果有三個L就return False，就算有四個L\(或以上\)也包含在這個condition裡。

