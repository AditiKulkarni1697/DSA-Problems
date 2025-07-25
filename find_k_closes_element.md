Approach:
we will find index from which the range will start. 
- for that we will consider mid to be the start of range 
- as the arr is in increasing order 
- we check if x is present in between m and m+k. 
- for that we substract mid from x and x from m+k
- if m+k is nearer to x compared to m we will move l = m+1
- else r = m

- we find 


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