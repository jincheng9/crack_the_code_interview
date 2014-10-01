Basic operations in Stacks and Queues:

(a) Stack: pop(), push(), top(), empty(), size()   (Implementation: array + a top pointer)

(b) Queue: enqueue(), dequeue(), front(), back(), empty(), size() (Implementation: array + a head pointer + a tail pointer)

###3.1 Describe how you could use a single array to implement three stacks.
Solution:

1. Use fixed array allocation for the three stacks, and then implement each stack on its own array space.

###3.2 Design a stack with three functions: push(), pop(), and min(). Push, pop, and min should all operate in O(1) time. min() returns the minimum element.
Solution:

1. 

### 3.5 Implement a MyQueue class which implements a queue with two stacks
Solution:

1. Stack A is used to add elements, Stack B is used to store the elements in A in reverse order. 
Enqueue() is done in stack A. Dequeue() is done in stack B.

Notice: the queue only needs to support the following operations: enqueue, dequeue, front, size. If the queue needs to support the operation "back" (access the last element of the queue), then the solutions of this book is wrong. 

### 3.6 Sort a stack in ascending order (with biggest items on top). You may use at most one additional stack to hold items, but you may not copy the elements into any other data structure (such as an array). The stack supports the following operations: push, pop, peek, and isEmpty.
Solution:

1. See the solutions of the book.

