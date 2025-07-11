/\*\*

- Definition for singly-linked list.
- function ListNode(val, next) {
-     this.val = (val===undefined ? 0 : val)
-     this.next = (next===undefined ? null : next)
- }
  \*/
  /\*\*
- @param {ListNode} head
- @param {number} k
- @return {ListNode}
  \*/
  var rotateRight = function(head, k) {
  if(!head || !head.next){
  return head
  }
  let sentinel = new ListNode()
  sentinel.next = head
  let length = 0;
  let n = head
  while(n){
  n=n.next
  length++
  }
  k = k%length
  for(let i=0;i<k;i++){
  let head = sentinel.next
  let node = head
  let prev = sentinel
  while(node && node.next){
  prev=node
  node=node.next

          }
          prev.next = null
          sentinel.next = node
          node.next = head
      }

      return sentinel.next

  };
