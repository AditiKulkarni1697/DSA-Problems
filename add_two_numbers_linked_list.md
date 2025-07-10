/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var addTwoNumbers = function(l1, l2) {

    let sentinel = new ListNode()
    let prev = sentinel
    let rev1 = l1
    let rev2 = l2

    let forward = 0;
    while(rev1 && rev2){
        let number = rev1.val + rev2.val + forward
        let node = new ListNode()
        if(number<10){
            node.val = number
            forward = 0
        }else{
            node.val = number%10
            forward = Math.floor(number/10)
        }
        prev.next = node
        prev = node
        rev1 = rev1.next
        rev2 = rev2.next
    }

    while(rev1){
        let number = rev1.val + forward
        let node = new ListNode()
        if(number<10){
            node.val = number
            forward = 0
        }else{
            node.val = number%10
            forward = Math.floor(number/10)
        }
        prev.next = node
        prev = node
        rev1 = rev1.next
    }

    while(rev2){
        let number = rev2.val + forward
        let node = new ListNode()
        if(number<10){
            node.val = number
            forward = 0
        }else{
            node.val = number%10
            forward = Math.floor(number/10)
        }
        prev.next = node
        prev = node
        rev2 = rev2.next
    }

    if(forward){
        let node = new ListNode()
        
            node.val = forward
        
        prev.next = node
        prev = node
    }
    return sentinel.next
    
};