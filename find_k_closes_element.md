Approach:
we will find index from which the range will start. 
- for that we will compare mid and mid+k. which ever is closer to x 
- if m is closer to x then we do r = m
- if m+k is closer to x then we do l = m+1


/**
 * @param {number[]} arr
 * @param {number} k
 * @param {number} x
 * @return {number[]}
 */
var findClosestElements = function(arr, k, x) {
    let l = 0;
    let r =  arr.length-1

    while(l<r){
        let m = l + Math.floor((r-l)/2)

        if((arr[m+k]-x)<(x-arr[m])){
            l = m+1
        }else{
            r = m
        }
    }

    let ans = arr.slice(l, l+k)
    return ans
};