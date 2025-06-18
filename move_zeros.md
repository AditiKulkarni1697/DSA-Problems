Given an integer array nums, move all 0’s to the end of it while maintaining the relative order of the non-zero elements.

Note: You must do this in-place without making a copy of the array.
Examples
Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]

Example 2:

Input: nums = [0]
Output: [0]

Constraints:

    1 <= nums.length <= 104
    -231 <= nums[i] <= 231 – 1


Solution:

/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
var moveZeroes = function(nums) {
    let i = 0;
    for(let j=0;j<nums.length;j++){
        if(nums[i]===0){
            nums[i] = nums[j]
            nums[j] = 0
        }
        if(nums[i]!==0){
            i++
        }
    }

};