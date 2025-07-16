/**
 * @param {number[]} temperatures
 * @return {number[]}
 */
var dailyTemperatures = function(temperatures) {
   let stack = []
    let n = temperatures.length
    let ans = Array(n).fill(0)
    for(let i=temperatures.length-1;i>=0;i--){
        while(stack.length && temperatures[i] >= stack[stack.length-1][0]){
            stack.pop()
            
        }
        if(!stack.length){
            ans[i] = 0
        }else{
            ans[i] = stack[stack.length-1][1]-i
        }
        stack.push([temperatures[i], i])
    }

    return ans
};