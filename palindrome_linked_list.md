Problem Statement:
Given the head of a singly linked list, return true if it is a palindrome or false otherwise.

Examples:
Input: head = [1,2,2,1]
Output: true
Input: head = [1,2]
Output: false
Constraints:
The number of nodes in the list is in the range [1, 105].
0 <= Node.val <= 9
Approach 1:
Traverse the linked list and store values in an array.
Check whether the array is a palindrome by comparing elements from start and end moving towards the center.
Time and Space Complexity:
Time Complexity: O(n), where n is the number of nodes.
Space Complexity: O(n), for the array storage.

/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */
var isPalindrome = function(head) {
    let arr = []
    let node = head;
    while(node){
        arr.push(node.val)
        node = node.next
    }
    let left = 0;
    let right = arr.length-1;
   // console.log(arr)
    while(left<=right){
        if(arr[left]===arr[right]){
            left++
            right--
        }else{
            return false
        }
    }
    return true

};

Or 


Approach:
1. find mid
2. reverse 2nd half
3. compare values of two halfs

/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {boolean}
 */
var isPalindrome = function(head) {
    if(!head || !head.next){
        return true
    }
    let slow = head;
    let fast = head;

    while(fast && fast.next && fast.next.next){
        slow = slow.next
        fast = fast.next.next
    }
    let mid = slow
    let prev = mid
    let curr = mid.next

    while(curr){
        let temp = curr.next
        curr.next = prev
        prev = curr
        curr = temp
    }
    let newHead = prev
    let left = head;
    let right = newHead
    while(left !== right && left!=mid.next && right!=mid){
        if(left.val === right.val){
            left = left.next
            right = right.next
        }else{
            return false
        }
    }
    return true
};