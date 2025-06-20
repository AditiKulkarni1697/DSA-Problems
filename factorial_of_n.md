Write a recursive function fact(n) that returns the factorial of a number n.
Concepts

    Recursion: Repeatedly multiply n with fact(n - 1).
    Base Case: fact(1) = 1
    Recursive Case: n * fact(n - 1)

Time & Space Complexity

    Time Complexity: O(n)
    Space Complexity: O(n) (recursive stack)

Examples

Input: 5
Output: 120 (5 * 4 * 3 * 2 * 1)

Solution:


function factorial(n) {
        // code here
        if(n==1){
            return 1
        }
        return n * factorial(n-1)
    }
    
    console.log(factorial(4))
