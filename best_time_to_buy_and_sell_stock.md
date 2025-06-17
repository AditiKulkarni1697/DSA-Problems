 You are given an array prices where prices[i] is the price of a given stock on the ith day.
You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.
Examples

Example 1:
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6 – 1 = 5.

Example 2:
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
Constraints

    1 <= prices.length <= 105
    0 <= prices[i] <= 104

Solution:

/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function(prices) {
    let i = 0;
    let max_p = 0;
    
    for(let j=0;j<prices.length;j++){
        if(prices[j]<prices[i]){
            i = j
        }else{
            max_p = Math.max(max_p, prices[j]-prices[i])
        }
    }

    return max_p
};