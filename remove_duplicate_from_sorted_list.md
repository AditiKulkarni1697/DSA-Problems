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
var deleteDuplicates = function(head) {
    let node = head;
    let temp = node;
    while(node){
        
        while(node && temp.val == node.val){
            node = node.next
        }
        temp.next = node
        temp = node
    }
    return head
};