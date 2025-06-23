Linked List

*IMportant for interviews

- linear data structure 
- nodes are linked together by a reference field

Two types of linked list:
1. Singly linked list
    - each node has a value
    - and address of next node

2. Doubly linked list
    - each node has a value
    - and address of both prev and next node

Head => head is starting node of a linked list

Difference between Linked list and Arrays 

Linked list                                      Arrays

- linear                                              -Linear
- non-contigeous                                      -contigeous
-Dynamic size(change easily)                          -Fixed size(can be dynamic)
- node = value + pointer                              -Just value
- Getting element is hard(O(n))                       - Getting element is easy O(1)
-insertion/deletion is easy(O(1))                     - Insertion/deletion is complex O(n)
- Extra memory                                        - Memory efficient


General Use cases of linked list and arrays

Access elements by index fast  => array

Insert/delete at head or tail frequently  =>  linked list

Memory-efficient storage for static size  => Array

Avoid resizing overhead or unknown size upfront  =>  Linked list

Do lots of traversal/manipulation  =>  Linked list