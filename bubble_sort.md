Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This process is repeated until the array is sorted. After each pass, the largest unsorted element “bubbles up” to its correct position at the end of the array. It’s called “Bubble Sort” because smaller elements slowly “bubble” to the top of the list. 

Solution:
/**
 * @param {number[]} arr
 */
class Solution {
    // Function to sort the array using bubble sort algorithm.
    bubbleSort(arr) {
        // code here
        let n = arr.length
        for(let i=0;i<n-1;i++){
            let swap = false
            for(let j=0;j<n-1-i;j++){
                if(arr[j]>arr[j+1]){
                    let temp = arr[j]
                    arr[j]=arr[j+1]
                    arr[j+1] = temp
                    swap = true
                }
            }
            
            if(!swap){
                return
            }
        }
    }
}

Or


/**
 * @param {number[]} arr
 */
class Solution {
    // Function to sort the array using bubble sort algorithm.
    bubbleSort(arr) {
        let swap = true
        // code here
        while(swap){
         swap =  false 
        for(let i=arr.length-1;i>0;i--){
            if(arr[i]<arr[i-1]){
                let temp = arr[i]
                arr[i] = arr[i-1]
                arr[i-1] = temp
                swap = true
            }
        }
        
        }
    }
}