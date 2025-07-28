/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
    let lengthA = 0;
    let lengthB = 0;
    let nodeA = headA
    let nodeB = headB

    while(nodeA){
        nodeA = nodeA.next
        lengthA++
    }

    while(nodeB){
        nodeB = nodeB.next
        lengthB++
    }

    nodeA = headA
    nodeB = headB
    let extra = Math.abs(lengthA - lengthB)
    if(lengthA > lengthB){
        while(extra){
           nodeA = nodeA.next 
           extra--
        }
    }else{
         while(extra){
           nodeB = nodeB.next 
           extra--
        }
    }

    while(nodeA && nodeB){
        if(nodeA == nodeB){
            return nodeA
        }else{
            nodeA = nodeA.next
            nodeB = nodeB.next
        }
    }
    return nodeA

};

Or 


Approach :
start pointers from head. compare pointers if not same go to next. when pointer reach null move pointer to 
another head. that way the pointer of small list will move to head of large list. and until the pointer of 
larger list reach null it will traverse through the difference between smaller and larger list.
So when pointer of larger list reacher null and then move to smaller list. the pointer of smaller list will be
at point from where the length of both list will be same.


/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */

/**
 * @param {ListNode} headA
 * @param {ListNode} headB
 * @return {ListNode}
 */
var getIntersectionNode = function(headA, headB) {
    let pA = headA
    let pB = headB

    while(pA !== pB){
        pA = pA === null ? headB : pA.next
        pB = pB === null ? headA : pB.next
    }
    return pA
};