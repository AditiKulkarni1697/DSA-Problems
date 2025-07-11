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
var swapPairs = function(head) {
    if(!head || !head.next){
        return head
    }
    let sentinel = new ListNode()
    let prev = sentinel
    let node = head

    while(node){
        if(node.next){
            let temp = node.next.next
            prev.next = node.next
            prev.next.next = node
            node.next = temp
            prev = node
            node = temp
        }else{
            node = node.next
        }
    }

    return sentinel.next
};