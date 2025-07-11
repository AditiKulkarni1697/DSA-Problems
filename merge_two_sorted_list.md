/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} list1
 * @param {ListNode} list2
 * @return {ListNode}
 */
var mergeTwoLists = function(list1, list2) {
    let sentinel = new ListNode()
    let prev = sentinel
    let node1 = list1
    let node2 = list2

    while(node1 && node2){
        if(node1.val>node2.val){
            prev.next = node2
            prev = node2
            node2 = node2.next
        }else{
            prev.next = node1
            prev = node1
            node1 = node1.next
        }
    }

    if(node1){
        prev.next = node1
    }

    if(node2){
        prev.next = node2
    }

    return sentinel.next
};