We normally do,

middle = (left+right)/2

although, it will work fine in JS, in other languages th sum it can overflow if the 
left and right are very large value. hence, follow below formula:

middle = left + ((right-left)/2)