/**
 * @param {string} s
 * @return {string}
 */
var removeOuterParentheses = function(s) {
    let ans = ""
    let stack = []
    for(let i=0;i<s.length;i++){
        if( stack.length >= 1  && s[i]==="("){
            ans += s[i]
            stack.push(i)

        }else if(stack.length > 1 && s[i]===")"){
            ans += s[i]
            stack.pop()
        }else if(stack.length < 1 && s[i]==="("){
            stack.push(i)
        }else if(stack.length == 1 && s[i]===")"){
            stack.pop()
        }
    }
    return ans
};