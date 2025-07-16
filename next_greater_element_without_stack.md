/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var nextGreaterElement = function(nums1, nums2) {
    let stack = []
    let ans = []

    for(let i=0;i<nums1.length;i++){
        let index;
        for(let j=0;j<nums2.length;j++){
            if(!index && nums1[i]===nums2[j]){
                index = j
                break;
            }

        }
        let value = -1
        for(let k=index+1;k<nums2.length;k++){
            if(nums2[index] < nums2[k]){
                value = nums2[k]
                break;
            }
        }
        ans.push(value)
        

    }

    return ans
};