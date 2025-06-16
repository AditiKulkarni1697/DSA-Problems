Star Pattern Programs in JavaScript, Java, C++, C, and Python
Pattern 1 – Print n x n Star Square

Print a square pattern of stars (*) of size n x n.
Example Output


****
****
****
****

Approach

    outer loop from i= 0 to n-1
    declare a variable and assign empty string to it
    inner loop from j = 0 to n-1
    concatinate a * into variable each time you visit a new j
    console the variable before going to next i

Time & Space Complexity

    Time Complexity: O(n^2)
    Space Complexity: O(n) (temporary row string)

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j < n; j++) {
    row += "*";
  }
  console.log(row);
}

Pattern 2 - Right-Angled Star Triangle Pattern

Write a program to print a right-angled triangle of stars (*) with n rows.
Example Output


*
**
***
****
  

Approach to Print Right-Angled Star Triangle

    Outer Loop (Rows): Run a loop from i = 0 to i = n - 1. Each iteration represents one row.
    Inner Loop (Stars per Row): For each row i, run another loop from j = 0 to j = i and append a * character to a string.
    Print Row: Print the string after the inner loop completes for each row.

Time & Space Complexity

    Time Complexity: O(n^2) because the total number of stars printed is 1 + 2 + ... + n = n(n+1)/2.
    Space Complexity: O(n) for the temporary string variable storing each row.

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += "*";
  }
  console.log(row);
}

Pattern 3 - Print a Right-Angled Number Triangle

Write a program that prints a right-angled triangle of numbers of height n.
Example Output


1
12
123
1234
  

Step-by-Step Approach

    Outer Loop (Rows): Run a loop from i = 0 to i < n. Each iteration represents a new row.
    Inner Loop (Numbers): Run an inner loop from j = 0 to j <= i, and append j + 1 to the row.
    Build and Print: Construct a string for the row and print it after the inner loop ends.

Time & Space Complexity

    Time Complexity: O(n²) — Each row can have up to n numbers.
    Space Complexity: O(n) — Temporary string to build each row.

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += (j + 1);
  }
  console.log(row);
}
    

Pattern 4 - Print a Right-Angled Triangle of Repeated Numbers

Write a program that prints a right-angled triangle where each row contains the same number repeated.
Example Output


1
22
333
4444
  

Step-by-Step Approach

    Outer Loop (Rows): Loop from i = 0 to i < n.
    Inner Loop (Repeated Numbers): Loop from j = 0 to j <= i, appending i + 1 as a string.
    Build and Print: Build the row string and print it.

Time & Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) — for the temporary row string

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += (i + 1);
  }
  console.log(row);
}
    

Pattern 5 - Print a Reverse Right-Angled Triangle of Increasing Numbers

Write a program that prints a reverse right-angled triangle where each row starts from 1 and the number of elements decreases with each row.
Example Output (n = 4)


1234
123
12
1
  

Approach

    Outer Loop (Rows): Loop i from 0 to n - 1. Each iteration represents a row.
    Inner Loop (Print Numbers): For each row, loop j from 0 to n - i - 1 and append j + 1 to a row string.
    Print Row: After the inner loop, print the row string.

Time and Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) for the temporary row string

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j < n - i; j++) {
    row += (j + 1);
  }
  console.log(row);
}
    

Pattern 6 - Print a Right-Aligned Right-Angled Triangle of Stars

Write a program that prints a right-aligned triangle of stars increasing row by row, with leading spaces for alignment.
Example Output (n = 4)


   *
  **
 ***
****
  

Approach

    Outer Loop (Rows): Loop i from 0 to n - 1. Each iteration is a new row.
    Inner Loop 1 (Spaces): For each row, add n - i - 1 spaces before the stars to right-align the triangle.
    Inner Loop 2 (Stars): Add i + 1 stars after the spaces.
    Print Row: Combine the spaces and stars, then print the row.

Time and Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) for the row string

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j < n - (i + 1); j++) {
    row += "_";
  }
  for (let k = 0; k < i + 1; k++) {
    row += "*";
  }
  console.log(row);
}

Or

Approach

    Outer Loop (Rows): Loop i from 0 to n - 1. Each iteration is a new row.
    Inner Loop 1 (Spaces): For each row, loop from j to n-1
    Inner Loop 2 (Stars): if j >= n-i-1 add * else add _.
    Print Row: Combine the spaces and stars, then print the row.

Time and Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) for the row string


let n = 4;
for (let i = 0; i < n; i++) {
    let row = "";
    for (let j = 0; j < n; j++) {
        if (j >= n - i - 1) {
            row += "*";
        } else {
          row += "_"
        }
    }
    console.log(row);
}
    

Pattern 7 - Print a Right-Angled Triangle of Alternating 1s and 0s

Write a program that prints a triangle of alternating 1s and 0s starting with 1 on each row.
Example Output (n = 4)


1
10
101
1010
  

Approach

    Outer Loop (Rows): Loop i from 0 to n - 1.
    Inner Loop : if j % 2 === 0 then add 1 else 0 from 0 to i
    Print Row: After inner loop, print the row string.

Time and Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) per row

let n = 4;
for (let i = 0; i < n; i++) {
  let row = "";
  
  for (let j = 0; j < i + 1; j++) {
    if(j%2===0){
      row += 1
    }else{
      row += 0
    }
    
  }
  console.log(row);
}

Pattern 8 - Right-Angled Triangle of Alternating 1s and 0s (Global Toggle)

Write a program to print a triangle of alternating 1s and 0s, but the toggle continues globally across rows.
Output (n = 4)


1
01
010
1010
  

Approach

    Global Toggle Variable: Declare toggle = 1 before the outer loop.
    Outer Loop: Loop i from 0 to n - 1.
    Inner Loop: Loop j from 0 to i. On each iteration:
        Append toggle to the row string.
        Flip toggle: 1 → 0 and 0 → 1.
    Print the row after the inner loop.

Key Difference

In the previous pattern, toggle = 1 was reset each row. Here, the toggle continues globally across the entire pattern.
Time & Space Complexity

    Time Complexity: O(n²)
    Space Complexity: O(n) per row

let n = 4;
let toggle = 1;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j < i + 1; j++) {
    row += toggle;
    toggle = toggle === 1 ? 0 : 1;
  }
  console.log(row);
}

