/**
 * @param {number[]} nums
 * @return {number}
 */
var findMin = function(nums) {
    let l =0;
    let r = nums.length-1
    let n = nums.length
    while(l<=r){
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid%n]<nums[(mid-1)%n] && nums[mid%n]<nums[(mid+1)%n]){
            return nums[mid]
        }else if(nums[mid]>nums[r]){
            l = mid+1
        }else{
            r = mid-1
        }
    }
    return nums[l]
    
};

Or

By checking sorted and unsorted portion and writing logic accordingly

/**
 * @param {number[]} nums
 * @return {number}
 */
var findMin = function(nums) {
    let l =0;
    let r = nums.length-1
    let n = nums.length
    while(l<=r){
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid]<nums[mid-1]){
            return nums[mid]
        }
        if(nums[l]==nums[r]){
            return nums[l]
        }
        if(nums[l] < nums[mid]){
            if(nums[l]<nums[r]){
                r=mid-1
            }else{
                l=mid+1
            }
        }else{
            if(nums[mid]<nums[r]){
                r=mid-1
            }else{
                l=mid+1
            }
        }
    }
    return nums[l]
    
};

Or 

by applying logic that the starting point will be in the unsorted array. if the arr has no unsorted part it means arr is already sorted

/**
 * @param {number[]} nums
 * @return {number}
 */
var findMin = function(nums) {
    let l =0;
    let r = nums.length-1
    let n = nums.length
    while(l<=r){
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid]<nums[mid-1]){
            return nums[mid]
        }
        if(nums[l]==nums[r]){
            return nums[l]
        }
        if(nums[l] > nums[mid]){
           r=mid-1
        }else{
            if(nums[mid] > nums[r]){
                l=mid+1
            }else{
                r=mid-1
            }
           
        }
    }
    return nums[l]
    
};