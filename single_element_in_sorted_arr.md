/**
 * @param {number[]} nums
 * @return {number}
 */
var singleNonDuplicate = function(nums) {
    let l = 0;
    let r = nums.length-1
    while(l<r){
        let mid = l + Math.floor((r-l)/2)
        if(mid%2==0){
            if(nums[mid]==nums[mid+1]){
                l = mid+2
            }else{
                r=mid
            }
        }else{
            if(nums[mid]==nums[mid+1]){
                r=mid-1
            }else{
                l=mid+1
            }
        }
    }
    return nums[r]
};