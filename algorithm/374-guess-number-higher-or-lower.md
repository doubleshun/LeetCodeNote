# \#374 Guess Number Higher or Lower

### Easy:star:

We are playing the Guess Game. The game is as follows:

I pick a number from `1` to `n`. You have to guess which number I picked.

Every time you guess wrong, I will tell you whether the number I picked is higher or lower than your guess.

You call a pre-defined API `int guess(int num)`, which returns 3 possible results:

* `-1`: The number I picked is lower than your guess \(i.e. `pick < num`\).
* `1`: The number I picked is higher than your guess \(i.e. `pick > num`\).
* `0`: The number I picked is equal to your guess \(i.e. `pick == num`\).

Return _the number that I picked_.

```text
# The guess API is already defined for you.
# @param num, your guess
# @return -1 if my number is lower, 1 if my number is higher, otherwise return 0
# def guess(num: int) -> int:

class Solution:
    def guessNumber(self, n: int) -> int:
        head = 1
        end = n
        while True :
            guess_number = (head+end)//2
            if guess(guess_number) == -1:
                end = guess_number-1
            elif guess(guess_number) == 1:
                head = guess_number+1
            else:
                return guess_number
```

