Given an integer x, return true if x is a

, and false otherwise.

 

Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

 

Constraints:

    -231 <= x <= 231 - 1


 Solution:

 /**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
    let reverse = ""
     
    let value = Math.abs(x)
    while(value>0){
        let remaining = value % 10
        reverse += remaining 
        value = Math.floor(value/10)
       
    }
    //console.log(x, reverse)
    if(x==reverse){
        return true
    }
    return false
};   

Optimized:

/**
 * @param {number} x
 * @return {boolean}
 */
var isPalindrome = function(x) {
    if(x < 0){
        return false
    }
    let reverse = 0;
    let value = x
    while(value>0){
        let remaining = value % 10
        reverse = (10 * reverse) + remaining 
        value = Math.floor(value/10)
       
    }
    //console.log(x, reverse)
    if(x===reverse){
        return true
    }
    return false
};