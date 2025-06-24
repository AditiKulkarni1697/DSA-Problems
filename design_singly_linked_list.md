1. Node - creating nodes in linked list - a node has two spaces in it 1.value 2.reference(next).

2. to create node we need to write function Node

function Node(val){
this.val = val;
this.next = null;
}

let newNode = new Node(5);  # this node will have value=5 and it refers to null



3. how to create a linked list

function myLinkedList(){
    this.head = null;
    this.size = 0;
}



var MyLinkedList = function() {
    this.head = null
    this.size = 0;
    
};

var newNode =function(val){
    this.val = val;
    this.next = null;
    return this.node
}
/** 
 * @param {number} index
 * @return {number}
 */
MyLinkedList.prototype.get = function(index) {
    let head = this.head
    let node = head
    let i = 0;
    while(i<index){
        node = node.next
        i++
    }
    return node.val
};

/** 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtHead = function(val) {
    let next = this.head
    this.head = new newNode(val);
    this.head.next = next
    
};

/** 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtTail = function(val) {
    let head = this.head
    let node = head

    while(node.next!=null){
        node = node.next
    }
    node.next = new newNode(val)

    console.log(node.val)
};

/** 
 * @param {number} index 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtIndex = function(index, val) {
    let head = this.head
    let node = head
    let i = 0;
    
    while(i<index-1 && node != null){
        node = node.next
        i++
    }
    if(node.next === null){
        node.next = new newNode(val)
        return node.next
    }
    if(node === null){
        return node
    }
    
    let temp = node.next
    node.next = new newNode(val)
    node.next.next = node.next
    console.log(node.val, node.next.val, node.next.next.val)
};

/** 
 * @param {number} index
 * @return {void}
 */
MyLinkedList.prototype.deleteAtIndex = function(index) {
     let head = this.head
    let node = head
    let i = 0;
    while(i<index-1){
        node = node.next
        i++
    }
    if(node.next === null){

        return node.next
    }
    if(node === null){
        return node
    }
    console.log(node.next.next.val)
    let temp = node.next.next
    node.next = temp
    
};

/** 
 * Your MyLinkedList object will be instantiated and called as such:
 * var obj = new MyLinkedList()
 * var param_1 = obj.get(index)
 * obj.addAtHead(val)
 * obj.addAtTail(val)
 * obj.addAtIndex(index,val)
 * obj.deleteAtIndex(index)
 */