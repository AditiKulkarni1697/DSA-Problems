/**
 * @param {string} s
 * @return {number}
 */
var lengthOfLastWord = function(s) {
    let i=s.length-1

    while(s[i]==" " && i>=0){
        i--
    }
    let j = i
    while(s[i]!=" " && i>=0){
        i--
    }

    return j - i
};