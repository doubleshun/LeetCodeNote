# \#121 Best Time to Buy and Sell Stock

### Easy:star:

Say you have an array for which the _i_th element is the price of a given stock on day _i_.  
If you were only permitted to complete at most one transaction \(i.e., buy one and sell one share of the stock\), design an algorithm to find the maximum profit.  
Note that you cannot sell a stock before you buy one.

```text
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max_price = 0
        for i in range(len(prices)-1):
            if prices[i+1:] != []:
                current_max_price = max(prices[i+1:]) - prices[i]
                if current_max_price > max_price : 
                    max_price = current_max_price
        return max_price
```

