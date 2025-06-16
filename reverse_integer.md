Question: Reverse Integer with Overflow Check

Write a function reverse(x) that takes a 32-bit signed integer and returns its digits reversed. If the reversed value overflows the 32-bit signed integer range, return 0.
Requirements

    Reverse the digits of a 32-bit signed integer.
    Return 0 if the result overflows.

Constraints

    Time Complexity: O(d) where d is the number of digits.
    Space Complexity: O(1) — constant space.

Example

Input: 123
Output: 321

Input: -123
Output: -321

Input: 1534236469
Output: 0 (overflow)

Solution:

/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
    let rev = 0;

    let negative = false;

    if(x<0){
        negative = true;
        x = Math.abs(x)
    }

    while(x>0){
        let rem = x % 10
        x = Math.floor(x/10)
        rev = (rev*10) + rem
    }

    if(negative){
        rev = rev * -1
    }

    if((-(2**31)) > rev || rev > (2**31 - 1)){
        return 0
    }
    return rev
};