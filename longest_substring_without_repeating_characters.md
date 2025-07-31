Appraoch:
when substring mentioned consider applying sliding window

- i = j = 0, obj={}
- check if j index value present in obj and if present is it before i or after i
- if j index value in obj is before i we assum the j index value is not in window and consider it valis window
- if j index value in obj is after i we assum the j value is in window and shrink the window until obj[s[j]]+1
- then we check if the window is max or not


/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLongestSubstring = function(s) {
    if(s.length == 0){
        return 0
    }
    if(s.length == 1){
        return 1
    }
    let i = 0;
    let j = 0;
    let obj = {}
    let maxLength = 0

    while(i<=j && j<s.length){
        
        
       if(obj[s[j]]!=undefined && obj[s[j]] >= i){
        i = obj[s[j]]+1
        obj[s[j]] = j
       }else{
        obj[s[j]] = j
       }
      // console.log(obj, i,j)
      maxLength = Math.max(maxLength, (j-i+1))
       j++
    }
    return maxLength
};