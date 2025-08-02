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

Or 

TimeComplexity ; O(N)
SpaceComplexity: O(26)

For small a = s.charCodeAt(index)-97
For captital A = s.charCodeAt(index)-65
1. take two arrays with 26 indexes filled with 0
2. iterate through s1 and (s2 until s1 length ) and fill the arrS and arrW with count of chars
3. now, check if the arrS and arrW is same, if yes return true
4. keep the window length constant and move the window to right side and check arrS and arrW again

/**
 * @param {string} s1
 * @param {string} s2
 * @return {boolean}
 */
var checkInclusion = function(s1, s2) {
    let arrS = Array(26).fill(0)
    let arrW = Array(26).fill(0)
    let windowL = s1.length

    for(let i=0;i<windowL;i++){
        ++arrS[s1.charCodeAt(i)-97]
        ++arrW[s2.charCodeAt(i)-97]
    }

    let k = 0
    let j = windowL-1
    while(j<s2.length){
        if(isSameChars(arrS, arrW)){
            return true
        }else{
            --arrW[s2.charCodeAt(k)-97]
            ++k
            
            ++j
            ++arrW[s2.charCodeAt(j)-97]
        }
    }
    return false
};

function isSameChars(arrS, arrW){
   
for(let i=0;i<arrS.length;i++){
    if(arrS[i]!=arrW[i]){
        return false
    }
}
return true
}