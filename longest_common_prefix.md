/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
  let comman = strs[0]

  for(let i=1;i<strs.length;i++){
    let j = 0
    while(strs[i][j] == comman[j] && j<strs[i].length){
        j++
    }
    comman = comman.substring(0,j)
  }
  return comman  
};

Or

/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
    let i = 0;
    while(i<strs[0].length){
        let char = strs[0][i]
        for(let j=1;j<strs.length;j++){
            if(strs[j].length <= i || char !== strs[j][i]){
                return strs[0].substring(0, i)
            }
        }
        i++
    }
    return strs[0]
};