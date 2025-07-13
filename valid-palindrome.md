/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function(s) {
    let characters = "abcdefghijklmnopqrstuvwxyz0123456789"
    let filtered = "";
    let reverse = "";
    s = s.toLowerCase()

    for(let i=0;i<s.length;i++){
        if(characters.includes(s[i])){
            filtered += s[i]
            reverse = s[i] + reverse
        }
    }

    return filtered === reverse

    
};



Or




/**
 * @param {string} s
 * @return {boolean}
 */
var isPalindrome = function(s) {
    let characters = "abcdefghijklmnopqrstuvwxyz0123456789"
    let i = 0;
    let j = s.length-1
    s = s.toLowerCase()

    while(i<j){
        while(!characters.includes(s[i]) && i<j){
            i++
        }
        while(!characters.includes(s[j]) && i<j ){
            j--
        }
        while(characters.includes(s[i]) && characters.includes(s[j]) && s[i]==s[j]){
            i++
            j--
        }
        if(characters.includes(s[i]) && characters.includes(s[j]) && s[i]!=s[j]){
            return false
        }
    }
    return true
};

