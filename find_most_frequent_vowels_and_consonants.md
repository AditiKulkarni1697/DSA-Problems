/**
 * @param {string} s
 * @return {number}
 */
var maxFreqSum = function(s) {
    let vowel = {a:0,e:0,i:0,o:0,u:0}
    let consonant = {}

    let i = 0;
    while(i<s.length){
        if(vowel[s[i]] != undefined){
            vowel[s[i]]++
        }else if(consonant[s[i]] != undefined){
            consonant[s[i]]++
        }else{
            consonant[s[i]] = 1
        }
        i++
    }

    let vowel_max = 0;
    let consonant_max = 0;

    for(key in vowel){
        if(vowel[key]>vowel_max){
            vowel_max = vowel[key]
        }
    }

    for(key in consonant){
        if(consonant[key]>consonant_max){
            consonant_max = consonant[key]
        }
    }

    return +vowel_max + +consonant_max
};