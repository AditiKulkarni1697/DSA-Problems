/**
 * @param {number[]} nums
 * @return {number[]}
 */
var nextGreaterElements = function(nums) {
    let ans = []
    let stack = []
    let n = nums.length
    for(let j=(2*n)-1;j>=0;j--){
        while(nums[j%n]>=stack[stack.length-1]){
            stack.pop()
        }
        if(stack.length){
            ans[j%n] = stack[stack.length-1]
            
        }else{
            ans[j%n] = -1

        }
        stack.push(nums[j%n])
    }

    return ans
};