Approach:

1. find left largest element for every index value excluding that index value
2. find right largest element for every index value excluding that index value
3. find which one is smaller out of left larest and right largest for that index
4. now substract your index value from that smaller one if index value is smaller than the smaller value
5. add those substraction result in sum variable 


/**
 * @param {number[]} height
 * @return {number}
 */
var trap = function(height) {
    let maxLeft = []
    let maxRight = []
    let min = []
    let sum = 0;
    let leftMax = 0;
    for(let i=0;i<height.length;i++){
        maxLeft[i] = leftMax
        if(height[i]>leftMax){
            leftMax = height[i]
        }
    } 
    let rightMax = 0
    for(let j=height.length-1;j>=0;j--){
        maxRight[j] = rightMax
        if(height[j]>rightMax){
            rightMax = height[j]
        }
    } 

    for(let k=0;k<maxRight.length;k++){
        
        if(maxLeft[k]<maxRight[k]){
            min[k] = maxLeft[k]
        }else{
            min[k] = maxRight[k]
        }
    }

    for(let l=0;l<min.length;l++){
        if(min[l]>height[l]){
            sum += min[l]-height[l]
        }
    }

    return sum

};