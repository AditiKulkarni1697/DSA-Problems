/**
 * @param {number[]} height
 * @return {number}
 */
var maxArea = function(height) {
  let l = 0;
  let r = height.length-1
  let maxArea = 0;
  while(l<r){
    let minHeight = Math.min(height[l], height[r])
    let area = minHeight * (r-l)
    //console.log(area, minHeight,(r-l-1))
    maxArea = Math.max(maxArea, area)
    if(height[l]<height[r]){
        l++
    }else{
        r--
    }
  }  
  return maxArea
};