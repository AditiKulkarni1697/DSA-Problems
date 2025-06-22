 Approach:

in arr = [4, 1, 3, 9, 7]

consider 0th index is already sorted

Start outer loop from 1st index. i = 1

start inner loop from 0.   j = 0

compare "i<j" 

if yes, store the arr[i] in temp variable and shift all elements from i-1 to j 
on index forward. and give arr[j] = temp 

/**
 *
 * insert
 * @param {number[]} arr
 * @param {number} i
 *
 * insertionSort
 * @param {number[]} arr
 * @param {number} n
 */
class Solution {

    // Please change the array in-place
    insertionSort(arr) {
        // code here
        for(let i=1;i<arr.length;i++){
            
            for(let j=0;j<i;j++){
                if(arr[i]<arr[j]){
                    let temp = arr[i]
                    for(let k=i-1;k>=j;k--){
                        arr[k+1] = arr[k]
                    }
                    arr[j] = temp
                }
            }
        }
    }
}

Or 

Approach:

let arr = [4, 1, 3, 9, 7]

start the loop from 1 iterate through all elements i=1
store the current element in temp 
now, store prev element in j. j=i-1
check if temp < arr[j] 
if yes, then shift the prev(j) element forward by 1

if no, then place the temp immediately ahead of prev(j)

/**
 *
 * insert
 * @param {number[]} arr
 * @param {number} i
 *
 * insertionSort
 * @param {number[]} arr
 * @param {number} n
 */
class Solution {

    // Please change the array in-place
    insertionSort(arr) {
        // code here
        for(let i=1;i<arr.length;i++){
            let temp = arr[i]
            let j = i-1
            while( temp<arr[j] && j>=0){
                
                arr[j+1] = arr[j]
                j--
               
           
            }
            arr[j+1] = temp
            
        }
    }
}