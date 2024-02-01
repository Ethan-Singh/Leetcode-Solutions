# 121. Best Time to Buy and Sell Stock

URL: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

So this one is pretty simple. You just need variables for the cheapest price you can buy it at so far, the currentProfit and the newProfit. You just compare if the newProfit is any better, and if it is then you take that value.

```java
class Solution {
    public int maxProfit(int[] prices) {
        
        int cheapest = Integer.MAX_VALUE;
        int currentProfit = Integer.MIN_VALUE;
        int newProfit = 0;
        
        for(int i = 0; i<prices.length; i++){
            if(prices[i]<cheapest){
                cheapest = prices[i];
            }
            newProfit = prices[i] - cheapest;
            if(currentProfit<newProfit){
                currentProfit = newProfit;
            }
        }
        
        return currentProfit;

    }
}
```