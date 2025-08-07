/**
 * @param {string} s
 * @return {number}
 */
var firstUniqChar = function(s) {
    let obj ={}
    for(let i=0;i<s.length;i++){
        if(obj[s[i]]==undefined){
            obj[s[i]]=1
        }else{
             obj[s[i]]++
        }
    }

    for(let key in obj){
        if(obj[key]==1){
            for(let j=0;j<s.length;j++){
               
                if(s[j]==key){
                    return j
                }
            }
        }
    }
    return -1
};