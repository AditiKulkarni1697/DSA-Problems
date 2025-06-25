1. Node - creating nodes in linked list - a node has two spaces in it 1.value 2.reference(next).

2. to create node we need to write function Node



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
    if(index<0  || index>=this.size){
        return -1
    }
    while(i<index && i<(this.size-1)){
        node = node.next
        i++
    }
    if(node === null){
        return -1
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
    this.size++
};

/** 
 * @param {number} val
 * @return {void}
 */
MyLinkedList.prototype.addAtTail = function(val) {
    let head = this.head
    let node = head
    let nodeNew = new newNode(val)
    if(node === null){
        this.head = nodeNew
        
    }else{
    while(node.next!=null){
        node = node.next
    }
    node.next = nodeNew
    }
    this.size++
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
    if(index<0 || index>this.size){
        return 
    }
     if(node === null){
        node = new newNode(val)
        this.head = node
        
    }else if(index === 0){
        this.addAtHead(val)
    }else{
    while(i<index-1 && node != null){
        node = node.next
        i++
    }
   
    if(node.next === null){
        this.addAtTail(val)
        
    }else{
    
    
    let temp = node.next
    node.next = new newNode(val)
    node.next.next = temp
    }
    }
    this.size++
//console.log(node.val, node.next.val,node.next.next.val, )
};

/** 
 * @param {number} index
 * @return {void}
 */
MyLinkedList.prototype.deleteAtIndex = function(index) {
     let head = this.head
    let node = head
    let i = 0;
    if(node === null){
        return 
    }
    if(index===0){
        //console.log(node.val,node.next.val,node.next.next.val)
        this.head = node.next
        node.next = null

        return 
    }
    while(i<index-1){
        node = node.next
        i++
    }
    if(node === null){
        return node
    }
    if(node.next === null){

        return node.next
    }
    
    let temp = node.next.next
    node.next = temp
    this.size--
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