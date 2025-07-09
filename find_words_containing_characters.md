/**
 * @param {string[]} words
 * @param {character} x
 * @return {number[]}
 */
var findWordsContaining = function(words, x) {
    let arr = []
    let i = 0;
    while(i<words.length){
        words[i].includes(x) ? arr.push(i) : "" ;
        i++
    }

    return arr
};