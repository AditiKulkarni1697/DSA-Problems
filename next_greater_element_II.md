/**
 * @param {number[]} nums
 * @return {number[]}
 */
var nextGreaterElements = function(nums) {
    let ans = []

    for(let i=0;i<nums.length;i++){
        let value = -1
        for(let j=i+1;j<(i+nums.length);j++){
            let index = j%nums.length
            if(nums[index] > nums[i]){
                value = nums[index]
                break;
            }
        }
        ans[i] = value
    }
return ans

};