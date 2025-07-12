/**
 * @param {string} s
 * @return {number}
 */
var balancedStringSplit = function(s) {
    let count = 0;
    let obj = {L:0, R:0}

    let i = 0;
    while(i<s.length){
     obj[s[i]]++

     if(obj["L"] === obj["R"]){
        count++
        obj["L"] = obj["R"] = 0
     }
        i++
    }

    return count
};