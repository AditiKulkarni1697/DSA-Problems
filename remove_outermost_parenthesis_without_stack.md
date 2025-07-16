/**
 * @param {string} s
 * @return {string}
 */
var removeOuterParentheses = function(s) {
    let count = 0;
    let substr = ""
    for(let i=0;i<s.length;i++){
        if(count == 0 && s[i]=="("){
            count++
        }else if(count > 0 && s[i]=="("){
            count++
            substr += s[i]
        }else if(count == 1 && s[i]==")"){
            count--
        }else if(count > 1 && s[i]==")"){
            count--
            substr += s[i]
        }
    }

    return substr
};