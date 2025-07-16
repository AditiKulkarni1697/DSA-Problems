/**
 * @param {string[]} tokens
 * @return {number}
 */
var evalRPN = function(tokens) {
    let stack = []
    

    for(let i=0;i<tokens.length;i++){
        if(!isNaN(tokens[i])){
            stack.push(tokens[i])
        }else{
            let top = stack.pop()
            let second = stack.pop()
            let ans = operation(+second,+top,tokens[i])
            stack.push(ans)
        }
    }

    return +stack[stack.length-1]
};

function operation(a,b,operator){
    if(operator === "+"){
        return a+b
    }else if(operator === "-"){
        return a-b
    }else if(operator === "*"){
        return a*b
    }else{
        return Math.trunc(a/b)
    }
}