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
    let slow = head
    let fast = head
    let sentinel = new ListNode()
    sentinel.next = head
for(let i=1;i<n;i++){
fast = fast.next
}

let prev = sentinel
while(fast.next){
    fast = fast.next
    prev = slow
    slow = slow.next
}

prev.next = prev.next.next

return sentinel.next

};