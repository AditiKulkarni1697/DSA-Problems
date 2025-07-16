/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number[]}
 */
var nextGreaterElement = function(nums1, nums2) {
    let stack = []

    for(let j=nums2.length-1;j>=0;j--){
        while(stack.length && stack[stack.length-1] < nums2[j]){
            stack.pop()
        }
        if(stack.length){
            nums2[j] = [nums2[j], stack[stack.length-1]]

        }else{
            nums2[j] = [nums2[j], -1]
        }
        stack.push(nums2[j][0])
    }

    for(let i=0;i<nums1.length;i++){
       
        for(let k=0;k<nums2.length;k++){
            if(nums1[i] === nums2[k][0]){
                nums1[i] = nums2[k][1]
                break;
            }
        }

    }
    return nums1
};