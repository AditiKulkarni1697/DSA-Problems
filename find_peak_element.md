/**
 * @param {number[]} nums
 * @return {number}
 */
var findPeakElement = function(nums) {
   
    let l = 0;
    let r = nums.length-1;
    
    while(l<r){
        let mid = l + Math.floor((r-l)/2)
        if((nums[mid]> nums[mid-1] || nums[mid-1] === undefined) && (nums[mid] > nums[mid+1] || nums[mid+1] === undefined)){
            return mid
        }else if(nums[mid] < nums[mid-1]){
            r = mid-1
        }else{
            l = mid+1
        }
    }
    return r
};