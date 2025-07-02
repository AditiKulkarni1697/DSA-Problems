/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} n
 * @return {ListNode}
 */
var removeNthFromEnd = function(head, n) {
    let length = 0;
    let node = head;

    while(node){
        node = node.next
        length++
    }

    node = head
    let nFromStart = (length - n)
    let sentinel = new ListNode()
    sentinel.next = head
    let prev = sentinel
    while(node && nFromStart){
        prev = node 
        node = node.next
        nFromStart--
    }
    prev.next = prev.next.next

    return sentinel.next
};