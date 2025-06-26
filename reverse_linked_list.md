
Problem Statement:

Given the head of a singly linked list, reverse the list, and return the reversed list.
Examples:

    Input: head = [1,2,3,4,5]
    Output: [5,4,3,2,1]
    Input: head = [1,2]
    Output: [2,1]
    Input: head = []
    Output: []

Constraints:

    The number of nodes in the list is in the range [0, 5000].
    -5000 ≤ Node.val ≤ 5000

Approach:

    Use three pointers: prev, curr, and next.
    In each step:
        Save the next node.
        Point current node’s next to previous.
        Move next, prev and curr forward.
    Return next as the new head.

Time and Space Complexity:

    Time Complexity: O(n), where n is the number of nodes in the list. We visit each node once.
    Space Complexity: O(1), since we reverse the list in-place using a constant number of pointers.

Solution:

/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
    if(head === null || head.next === null){
        return head
    }
    
    let prev = null
    let curr = head 
    let next = head.next

    while(next && next.next){
        curr.next = prev
        prev = curr
        curr = next
        next = next.next
    }
    next.next = curr
    curr.next = prev
    return next
};