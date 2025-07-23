/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var searchRange = function(nums, target) {
    let l = 0;
    let r = nums.length-1
    while(l<=r){
        if(nums[l]==target && nums[r]==target){
            return [l,r]
        }
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid]<target){
            l=mid+1
        }else if(nums[mid]>target){
            r=mid-1
        }else{
            if(nums[l]<target){
                l++
            }
            if(nums[r]>target){
                r--
            }
        }
    }
    return [-1,-1]
};