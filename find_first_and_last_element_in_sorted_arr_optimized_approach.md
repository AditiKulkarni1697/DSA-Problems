/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var searchRange = function(nums, target) {
     let l = 0;
    let r = nums.length-1
    let ans = []
    while(l<=r){
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid]<target){
            l = mid+1
        }else if(nums[mid]>target){
            r=mid-1
        }else{
            if(nums[mid-1]!=nums[mid]){
                ans[0] = mid
                l = r+1
            }else{
                r=mid-1
            }
        }
    }
    ans[0] == undefined ? ans[0]=-1 : null

      l = 0;
       r = nums.length-1
    while(l<=r){
        let mid = l + Math.floor((r-l)/2)
        if(nums[mid]<target){
            l = mid+1
        }else if(nums[mid]>target){
            r=mid-1
        }else{
            if(nums[mid+1]!=nums[mid]){
                ans[1] = mid
                l=r+1
            }else{
                l=mid+1
            }
        }
    }
    ans[1] == undefined ? ans[1]=-1 : null;
    return ans
};