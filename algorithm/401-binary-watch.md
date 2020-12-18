# \#401 Binary Watch

### Easy:star:

A binary watch has 4 LEDs on the top which represent the **hours** \(**0-11**\), and the 6 LEDs on the bottom represent the **minutes** \(**0-59**\).

Each LED represents a zero or one, with the least significant bit on the right.

```text
class Solution:
    def readBinaryWatch(self, num: int) -> List[str]:
        from itertools import combinations
        items = ['1H','2H','4H','8H','1M','2M','4M','8M','16M','32M']
        values = [1,2,4,8,1,2,4,8,16,32]
        dict_items = dict(zip(items, values))
        combinations_list = []
        for c in combinations(items, num):
            hour = 0
            minute = 0
            clock = ''
            for i in range(len(c)):
                if 'H' in c[i]:
                    hour += dict_items[c[i]]
                else:
                    minute += dict_items[c[i]]
            if hour < 12 and minute < 60 :
                clock += str(hour)
                clock += ':'
                if minute < 10 :
                    clock += '0'+str(minute)
                else:
                    clock += str(minute)
                combinations_list.append(clock)
        return sorted(combinations_list)
```

