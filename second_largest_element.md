Second Largest

Difficulty: Easy
Accuracy: 26.72%
Submissions: 1.2M
Points: 2
Average Time: 15m

Given an array of positive integers arr[], return the second largest element from the array. If the second largest element doesn't exist then return -1.

Note: The second largest element should not be equal to the largest element.

Examples:

Input: arr[] = [12, 35, 1, 10, 34, 1]
Output: 34
Explanation: The largest element of the array is 35 and the second largest element is 34.

Input: arr[] = [10, 5, 10]
Output: 5
Explanation: The largest element of the array is 10 and the second largest element is 5.

Input: arr[] = [10, 10, 10]
Output: -1
Explanation: The largest element of the array is 10 and the second largest element does not exist.

Constraints:
2 ≤ arr.size() ≤ 105
1 ≤ arr[i] ≤ 105


Algorithm: 

1. Go through the array, if you find current value greater than max, then assign max value to 
   second_max value and current value to max.
2. else if a current value is greater than second_max and current value is less than max, then assign 
   current value to second_max.


Solution:

 getSecondLargest(arr) {
        // code here
        let max = -1;
        let second = -1;
        
        for(let i=0;i<arr.length;i++){
            if(arr[i]>max){
                second = max
                max = arr[i]
                
            }
            else if(arr[i]>second && arr[i]<max){
                second = arr[i]
                
            }
        }
        
        return second
    }