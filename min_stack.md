
var MinStack = function() {
    this.minStack = []
    this.stack =  []
};

/** 
 * @param {number} val
 * @return {void}
 */
MinStack.prototype.push = function(val) {
    if(!this.minStack.length || this.minStack[this.minStack.length-1]>=val){
        this.minStack.push(val)
    }

    this.stack.push(val)
};

/**
 * @return {void}
 */
MinStack.prototype.pop = function() {
    let ele = this.stack.pop()
    if(this.minStack[this.minStack.length-1]==ele){
        this.minStack.pop()
    }
};

/**
 * @return {number}
 */
MinStack.prototype.top = function() {
    return this.stack[this.stack.length-1]
};

/**
 * @return {number}
 */
MinStack.prototype.getMin = function() {
    return this.minStack[this.minStack.length-1]
};

/** 
 * Your MinStack object will be instantiated and called as such:
 * var obj = new MinStack()
 * obj.push(val)
 * obj.pop()
 * var param_3 = obj.top()
 * var param_4 = obj.getMin()
 */