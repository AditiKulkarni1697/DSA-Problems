
// Write a recursive function sum(n) that calculates the sum of all odd numbers in an array arr up to index n.
//   Concepts

// Recursion: Repeatedly check whether arr[n] is odd, and add it only if true.
//     Base Case: If n == 0, return arr[0] if it’s odd, otherwise 0.
//     Recursive Case: Return(arr[n] if odd) + sum(n - 1).

//   Time & Space Complexity

//     Time Complexity: O(n)
//     Space Complexity: O(n)(recursive call stack)

// Examples

let arr = [5, 2, 6, 1, 3]
// Odd numbers: 5, 1, 3
// Output: 9

function oddSum(n) {
  if (n == 0) {
    if (arr[0] % 2 === 1) {
      return arr[0]
    } else {
      return 0
    }
  }

  let sum = arr[n] % 2 === 1 ? arr[n] : 0
  return sum + oddSum(n-1)
}

console.log(oddSum(arr.length-1))