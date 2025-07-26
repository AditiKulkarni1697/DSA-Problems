/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    let i = 0;
    let j = needle.length-1
    while(j<haystack.length){
        let sub = haystack.slice(i,j+1)
        //console.log(sub)
        if(sub === needle){
            return i
        }else{
            i++
            j++
        }
    }
    return -1
};

Or 

/**
 * @param {string} haystack
 * @param {string} needle
 * @return {number}
 */
var strStr = function(haystack, needle) {
    let n = haystack.length
    let m = needle.length

    for(let i=0;i<=n-m;i++){
        let j = 0;
        for(j=0;j<m;j++){
            if(haystack[i+j]!=needle[j]){
                break;
            }
        }
        if(j==m){
            return i
        }
    }
    return -1
};