Problem Statement:
Given the heads of two singly linked-lists headA and headB, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return null.

Examples:
Input: intersectVal = 8, listA = [4,1,8,4,5], listB = [5,6,1,8,4,5], skipA = 2, skipB = 3
Output: Intersected at ‘8’
Input: intersectVal = 2, listA = [1,9,1,2,4], listB = [3,2,4], skipA = 3, skipB = 1
Output: Intersected at ‘2’
Input: intersectVal = 0, listA = [2,6,4], listB = [1,5], skipA = 3, skipB = 2
Output: No intersection
Constraints:
The number of nodes in each list is in the range [0, 10⁴].
-10⁵ ≤ Node.val ≤ 10⁵
Lists are guaranteed to be acyclic and maintain their structure.
Approach:
1.count the total nodes in every linked list
2.substract smaller from larger count
3. run the larger linked list upto diff
4. and then compare every node of linked list A and B

Time and Space Complexity:
Time Complexity: O(n + m), where n and m are lengths of listA and listB.
Space Complexity: O(m), storing nodes of listB in a set.

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
    let countA = count(headA);
    let countB = count(headB);
 
    if(!countA || !countB){
        return null
    }
    if(headA === headB){
        return headA
    }

    let larger = countA>countB ? headA : headB
    let smaller = larger === headA ? headB : headA
    let diff = countA>countB ? countA-countB : countB-countA

    let largerNode = 0;
    while(larger && largerNode<diff){
        larger = larger.next
        largerNode++
    }
    while(larger && smaller && larger !== smaller){
        larger = larger.next
        smaller = smaller.next
    }

    if(larger && smaller){
        return larger
    }else{
        return null
    }

};

var count = function(head){
  let nodeCount = 0;
  let node = head
  while(node){
    nodeCount++
    node = node.next
  }
  return nodeCount
}

Or 

Approach:
1. store all linkedlist B nodes in a set
2. now traverse through linked list a and check if the node is present in set


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
    let newSet = new Set();

    let nodeB = headB
    while(nodeB){
        newSet.add(nodeB)
        nodeB = nodeB.next
    }

    let nodeA = headA
    while(nodeA){
        if(newSet.has(nodeA)){
            return nodeA
        }
        nodeA = nodeA.next
    }

    return nodeA

};