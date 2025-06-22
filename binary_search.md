 Binary Search is an efficient algorithm used to find the position of a target value within a sorted array. Unlike linear search, it repeatedly divides the search interval in half, significantly reducing the number of comparisons.
Approach

    Set left = 0, right = nums.length - 1.
    While left <= right:
        Calculate middle = Math.floor((left + right) / 2).
        If nums[middle] === target, return middle.
        If target < nums[middle], discard the right half: right = middle - 1.
        Else, discard the left half: left = middle + 1.
    If the target is not found, return -1.

Example:

Given array: [1, 3, 5, 7, 9]
Target: 7 

Solution:

/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var search = function(nums, target) {
    let start = 0;
    let end = nums.length-1;

    while(start<=end){
        let mid = Math.floor((start+end)/2)

        if(nums[mid] === target){
            return mid
        }

        if(nums[mid] > target){
            end = mid-1
        }else{
            start = mid+1
        }
    }

    return -1
};