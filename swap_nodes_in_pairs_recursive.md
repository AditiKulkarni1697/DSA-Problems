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
    let sentinel = new ListNode()
    sentinel.next = head

    swap(sentinel, head)

    return sentinel.next
};

var swap = function(prev,node){
 if(!node || !node.next){
    return
 }

 prev.next = prev.next.next
 node.next = node.next.next
 prev.next.next = node
 swap(node, node.next)
}