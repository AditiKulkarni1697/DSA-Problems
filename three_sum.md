/**
 * @param {number[]} nums
 * @return {number[][]}
 */
var threeSum = function(nums) {
    
    let ans = [];
    nums = nums.sort((a,b)=>a-b)
    for(let i = 0;i<nums.length;i++){
        let sum = -nums[i]

        let j=i+1;
        let k = nums.length-1
        while(j<k){
            if(nums[j] + nums[k] == sum){
                ans.push([nums[i], nums[j], nums[k]])
               
                while(j<k-1 && nums[j]==nums[j+1]){
                    j++
                }
                while(j<k-1 && nums[k]==nums[k-1]){
                    k--
                }
                j++
                k--
            }else if(nums[j] + nums[k] > sum){
                k--
            }else{
                j++
            }
           

        }
        while(i<nums.length-1 && nums[i]==nums[i+1]){
            i++
        }
    }
    
    return ans

};