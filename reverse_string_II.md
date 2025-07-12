/**
 * @param {string} s
 * @param {number} k
 * @return {string}
 */
var reverseStr = function(s, k) {
   
    for(let i=2*k; i<s.length+(2*k)-1 ;i+=2*k){
        let first = s.substring(0, i-(2*k))
        let sub = s.substring(i-(2*k), i-k)
        let remaining =  s.substring(i-k)
        sub = sub.split("").reverse().join("")
        //console.log(sub, remaining)
        s = first + sub + remaining
    }
    return s


};

Or 

/**
 * @param {string} s
 * @param {number} k
 * @return {string}
 */
var reverseStr = function(s, k) {
    s = s.split("")

    for(let i=0;i<s.length;i=i+2*k){
        let start = i;
        let end = i+k-1
        while(start<end){
            let temp = s[start]
            s[start] = s[end]
            s[end] = temp
            start++
            end--
        }

    }

    return s.join("")
};