/**
 * Definition for isBadVersion()
 * 
 * @param {integer} version number
 * @return {boolean} whether the version is bad
 * isBadVersion = function(version) {
 *     ...
 * };
 */

/**
 * @param {function} isBadVersion()
 * @return {function}
 */
var solution = function(isBadVersion) {
    /**
     * @param {integer} n Total versions
     * @return {integer} The first bad version
     */
    return function(n) {
        if(isBadVersion(1)){
            return 1
        }
        let l = 1;
        let r = n
        while(l<r){
            let mid = l + Math.floor((r-l)/2)
            if(isBadVersion(mid)){
                    r = mid
                
            }else{
                l = mid+1
            }
    
        }
        return r
    };
};


*** when you are not sure if mid is answer or not include it in search space

*** run while loop until l<=r only when you are moving both l and r pointers by same value otherwise run while loop until l<r