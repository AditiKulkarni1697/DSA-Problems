Approach:
1. i = 0, obj = {}, and i will iterate through s string
2. if the current index present in obj i will increase the count else do obj[s[j]]=1
3. now, i will go through the map, and check which element has max count
4. i will substract that max count from total window length, if the diff is less than k then window is valid
5. else we will move our window to right side by 1.

/**
 * @param {string} s
 * @param {number} k
 * @return {number}
 */
var characterReplacement = function(s, k) {
    let i = 0;
    let obj = {}
    let ans = 0
    for(let j=0;j<s.length;j++){
        if(obj[s[j]]==undefined){
            obj[s[j]]=1
        }else{
            obj[s[j]]++
        }
        let max = 0;
        let total = j-i+1
        for(let key in obj){
            if(max<obj[key]){
                max = obj[key]
            }
            
        }
        if(k < (total-max)){
            obj[s[i]]--
            i++
        }else{
            ans = Math.max(ans, j-i+1)
        }
    }
    return ans
};

Or 

var characterReplacement = function(s, k) {
    let i = 0, j = 0;
    let map = Array(26).fill(0);
    map[s.charCodeAt(0) - 65] = 1;
    let maxWindow = 0;
    while (j < s.length) {
        if (isWindowValid(map, k)) {
            maxWindow = Math.max(maxWindow, j - i + 1);
            ++j;
            ++map[s.charCodeAt(j) - 65];
        } else {
            --map[s.charCodeAt(i) - 65];
            ++i;
        }
    }
    return maxWindow;  
};
var isWindowValid = function(map, k) {
    let totalCount = 0;
    let maxCount = 0;
    for (let i = 0; i < 26; i++) {
        totalCount += map[i];
        maxCount = Math.max(maxCount, map[i]);
    }
    return (totalCount - maxCount <= k);
};