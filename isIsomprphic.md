/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isIsomorphic = function(s, t) {
    let sObj = {}
    let tObj = {}

    for(let i=0;i<s.length;i++){
        if(sObj[s[i]] === undefined && tObj[t[i]] === undefined){
            sObj[s[i]] = t[i]
            tObj[t[i]] = s[i]
        }else if(sObj[s[i]] === undefined && tObj[t[i]] != undefined){
            return false
        }else if(sObj[s[i]] != undefined && sObj[s[i]] != t[i]){
            return false
        }
    }

    return true
};