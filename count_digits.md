Write a function countDigits(n) that takes an integer n and returns how many digits it contains.
Requirements

    Handles both positive and negative integers.
    Return 1 if n is 0 (since 0 is a single-digit number).

Constraints

    Time Complexity: O(log₁₀(n)) — Each division reduces one digit.
    Space Complexity: O(1) — Only a few variables are used.

Examples

Input: 259
Output: 3

Input: -1035
Output: 4

Input: 0
Output: 1

Approach:

1. handle corner case of input = 0, by returning 1
2. handle corner case of having negative number by using Math.abs
3. define a variable count 
4. Keep dividing the value with 10 until value is 0, and count divisions
5. use Math.floor() before assigning new value

Solution:

let count = 0;

if (input === 0) {
    count = 1
    
}
while (input !== 0) {
    input = Math.abs(input)
    input = input / 10
    count++
    input = Math.floor(input)
}

console.log(count)