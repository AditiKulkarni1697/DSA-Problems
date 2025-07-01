/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @param {number} val
 * @return {ListNode}
 */
var removeElements = function(head, val) {
    let node = head;
    let sentinle = new ListNode()
    sentinle.next = head

    let prev = sentinle
    if(!head){
        return head
    }
    while(node){
        if(node.val === val){
           prev.next = node.next
           node = prev.next
        }else{
        prev = node
        node = node.next
        }
    }
    return sentinle.next
};


