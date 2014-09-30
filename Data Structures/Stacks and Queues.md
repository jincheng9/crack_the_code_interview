Basic concepts in Stacks and Queues:

(a) Stack: pop(), push(), top(), empty(), size()   (array + a top pointer)

(b) Queue: enqueue(), dequeue(), front(), back(), empty(), size() (array + a head pointer + a tail pointer)

###3.1 Describe how you could use a single array to implement three stacks.
Solution:

1. Use fixed array allocation for the three stacks, and then implement each stack on its own array space.

###3.2 Design a stack with three functions: push(), pop(), and min(). Push, pop, and min should all operate in O(1) time. min() returns the minimum element.
Solution:

1. 