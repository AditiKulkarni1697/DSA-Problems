Approach:
1. here, we maintain a dequeue(a queue which can pop and can see element at end)
2. while the window size is less than k we compare the curr element with last ele of 
dequeue. while curr ele is greater we pop the last element. and then we push curr ele to dequeue
3. once window length is equal to k, then after poping all smaller elements and pushing the curr ele to dequeue, we push 1st element of dequeue to ans arr. bcoz that ele will be largest in the window.
4. to slide window to right, we need to do start++. before doing start++ we check if start is our greatest ele
by comparing start and dequeue front ele. if yes, we do dequeue.unshift() and then do start++.
5. such dequeue is also called "monotonic decreasing dequeue"



/**
 * @param {number[]} nums
 * @param {number} k
 * @return {number[]}
 */
var maxSlidingWindow = function(nums, k) {
  
    let ans = []
    let start = 0
    let queue = [nums[0]]
    let n = queue.length-1
    for(let j=1;j<k;j++){
       
        while(queue.length && queue[queue.length-1]<nums[j]){
            queue.pop()
            
        }
         queue.push(nums[j])
    }
    ans.push(queue[0])
    if(queue[0]==nums[start]){
        queue.shift()
    }
    start = 1
    for(let i=k;i<nums.length;i++){
    
     
        while(queue.length && queue[queue.length-1]<nums[i]){
            queue.pop()
            
        }
        queue.push(nums[i])
        ans.push(queue[0])
        if(queue[0]==nums[start]){
        queue.shift()
       
    }
    
        start++
     }
    return ans

};