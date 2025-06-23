What is Merge Sort?

Merge Sort is a popular divide-and-conquer sorting algorithm that divides the input array into two halves, recursively sorts them, and then merges the sorted halves into one sorted result.

It is an example of a stable sort that guarantees O(n log n) performance in all cases — best, worst, and average.

Aprroach:

keed divideing arrays in half until arr.length <= 1

i.e. single element is present in array. return that array 

now, merge the two halfs in sorted manner using a helper function


Time complexity =>

the diviing arrays in two halfs takes logn time complexity 
and merging the two arrays takes n times complexity 
hence, the time complexity is O(nlogn)

Space Complexity:
As we create new array for merging the space complexity is O(n)

/**
 * @param {number[]} nums
 * @return {number[]}
 */
var sortArray = function(nums) {
    if(nums.length<=1){
        return nums
    }

    let mid = Math.floor((nums.length-1)/2)

    let arr1 = []
    for(let i=0;i<=mid;i++){
        arr1.push(nums[i])
    }
    let arr2 = []
    for(let j=mid+1;j<=nums.length-1;j++){
        arr2.push(nums[j])
    }

    let left = sortArray(arr1)
    let right = sortArray(arr2)
    return merge(left,right)
};

var merge = function(arr1,arr2){
    let merged = []
    let i = 0
    let j = 0

    while(i<arr1.length && j<arr2.length){
        if(arr1[i]<arr2[j]){
            merged.push(arr1[i])
            i++
        }else{
             merged.push(arr2[j])
            j++
        }
    }

    while(i<arr1.length){
        merged.push(arr1[i])
            i++
    }

    while(j<arr2.length){
        merged.push(arr2[j])
            j++
    }

    return merged
}