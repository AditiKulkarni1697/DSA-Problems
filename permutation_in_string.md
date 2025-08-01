/**
 * @param {string} s1
 * @param {string} s2
 * @return {boolean}
 */

 approach:
 0. create two objs (s1obj and s2obj)containing a to z with value 0 
 1. create obj of s1 str
 2. now iterate through s2 using k.
 3. keep a pointer start at 0
 4. if difference between start and k is greater than s1.length then remove start value from s2obj and push start pointer to right
 5. push the k value to s2obj in both case 
 6. now, compare both objects by stringifying values 
 7. if strings are same return true
 
var checkInclusion = function(s1, s2) {
    let char = "abcdefghijklmnopqrstuvwxyz"
    let s1obj = {}
    let s2obj = {}
    for(let i=0;i<char.length;i++){
        s1obj[char[i]] = 0
        s2obj[char[i]] = 0
    }
      
    for(let j=0;j<s1.length;j++){
        s1obj[s1[j]]++
    }
    let str1 = ""
    for(let key in s1obj){
        str1 += s1obj[key]
      }

    let n = s1.length-1
    let start = 0
    for(let k=0;k<s2.length;k++){
     if(k-start > n){
      --s2obj[s2[start]]
      ++start
     }
     ++s2obj[s2[k]]

     let str2 = ""
    for(let key in s2obj){
        str2 += s2obj[key]
      }
     // console.log(str1,str2)
      if(str1 == str2){
        return true
      }
    }
    return false


};