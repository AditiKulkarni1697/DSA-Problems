Write a function sum(n) that calculates the sum of all numbers in an array arr using recursion. It sums from index 0 to n.
Concepts

    Recursion: The function keeps summing the element at index n and calls itself with n-1.
    Base Case: If n == 0, return the first element.
    Recursive Case: Return arr[n] + sum(n - 1).

Time & Space Complexity

    Time Complexity: O(n) – one recursive call per element.
    Space Complexity: O(n) – due to call stack.

Examples

Input: [5, 2, 6, 1, 3]
Output: 17
// 5 + 2 + 6 + 1 + 3 = 17

Solution:

function sum(n) {
  if (n==1) {
    return 1
  }
  return n+sum(n-1)
}

const total = sum(5)

console.log(total)