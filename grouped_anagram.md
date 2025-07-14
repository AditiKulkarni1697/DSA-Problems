/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function(strs) {
    let obj = {}

    for(let i=0;i<strs.length;i++){
        let sorted = strs[i].split("").sort().join("")
        if(!obj[sorted]){
            obj[sorted] = [strs[i]]
        }else{
            obj[sorted].push(strs[i])
        }
    }

    let ans = []
    for(let key in obj){
        ans.push(obj[key])
    }

    return ans
};