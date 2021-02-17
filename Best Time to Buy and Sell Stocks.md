[Question link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock)

Brute Force Approach - 
```js
var maxProfit = function(prices) {
    let soln = [0];
    for(let i = 0; i<prices.length ; i++){
        for(let j = i+1; prices.length; j++){
            if(prices[j] > prices [i])
                soln.push(prices[j]-prices[i])
        }
    }
    let max = soln[0];
    for(let i = 1; i<soln.length; i++){
        if(max<soln[i])
            max = soln[i]
    }
    return max
}
```

Optimized Solution - 
```js
var maxProfit = function(prices) {
    let min = prices[0];
    let diff = 0;
    for(let i = 1; i<prices.length; i++){
        if(min > prices[i]){
            min = prices[i]
        }else if(diff < prices[i]-min){
            diff = prices[i]-min
        }
    }
    return diff;
}
```
