Problem Statement:
Given head, the head of a linked list, determine if the linked list has a cycle in it. Return true if there is a cycle; otherwise, return false.

Examples:
Input: head = [3,2,0,-4], pos = 1
Output: true
Input: head = [1,2], pos = 0
Output: true
Input: head = [1], pos = -1
Output: false
Constraints:
The number of nodes is in the range [0, 10⁴].
-10⁵ ≤ Node.val ≤ 10⁵
pos is -1 or a valid index in the linked list.
Approach:

floyd's alogorithm - if cycle exists slow and fast will meet at a point.
we took two variables slow and fast
slow = slow.next
fast = fast.next.next
when slow === fast then it has loop 
if fast === null then no loop

Time Complexity: O(n), where n is the number of nodes in the list.
Space Complexity: O(1)

/**
 * @param {Node} head
 * @returns {boolean}
 */

/*
class Node{
    constructor(data){
        this.data = data;
        this.next = null;
    }
}
*/

class Solution {
    // Function to check if the linked list has a loop.
    detectLoop(head) {
        // your code here
        if(head === null || head.next === null || head.next.next===null){
            return false
        }
        let slow = head.next;
        let fast = head.next.next;
        
        while(slow != fast && fast != null){
            slow = slow?.next
            fast = fast?.next?.next
        }
        
        
        if(slow === fast){
            return true
        }
        if(fast === null){
            return false
        }
    }
}

Or 

/**
 * @param {Node} head
 * @returns {boolean}
 */

/*
class Node{
    constructor(data){
        this.data = data;
        this.next = null;
    }
}
*/

class Solution {
    // Function to check if the linked list has a loop.
    detectLoop(head) {
        // your code here
        let newSet = new Set()
        let node = head
        while(!newSet.has(node)&&node != null){
            newSet.add(node)
            node = node.next
        }
        
        if(node === null){
            return false
        }else{
            return true
        }
    }
}