
Time Complexixy => O(nlogm)
Space complexity => O(nm)
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

Or 

Time Complexixy => O(nm)
Space complexity => O(nm)

/**
 * @param {string[]} strs
 * @return {string[][]}
 */
var groupAnagrams = function(strs) {
    let obj = {}

    for(let i=0;i<strs.length;i++){
        let freqArr = new Array(26).fill(0)
        for(let j=0;j<strs[i].length;j++){
            let index = strs[i].charCodeAt(j) - "a".charCodeAt()
            freqArr[index]++
        }
        let key = freqArr.join(",")

        if(!obj[key]){
            obj[key] = [strs[i]]
        }else{
            obj[key].push(strs[i])
        }

    //console.log(obj)
    }
    let ans = []

    for(let key in obj){
        ans.push(obj[key])
    }

    return ans
};