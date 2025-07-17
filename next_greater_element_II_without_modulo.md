/**
 * @param {number[]} nums
 * @return {number[]}
 */
var nextGreaterElements = function(nums) {
    let ans = []
    let stack = []

    for(let i=nums.length-1;i>=0;i--){
        stack.push(nums[i])
    }

    for(let j=nums.length-1;j>=0;j--){
        while(nums[j]>=stack[stack.length-1]){
            stack.pop()
        }
        if(stack.length){
            ans[j] = stack[stack.length-1]
            
        }else{
            ans[j] = -1

        }
        stack.push(nums[j])
    }

    return ans
};