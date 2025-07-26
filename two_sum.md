/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let obj = {}

    for(let i=0;i<nums.length;i++){
        if(obj[nums[i]] != undefined){
            return [obj[nums[i]], i]
        }else{
            let rem = target - nums[i]
            obj[rem] = i
        }
    }
   // console.log(obj)
};

Or

/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let obj = {}
    for(let i=0;i<nums.length;i++){
        obj[nums[i]] = i
    }

    for(let j=0;j<nums.length;j++){
        let rem = target - nums[j]
        if(obj[rem]!=undefined && obj[rem]!=j){
            return [obj[rem], j]
        }
    }
};