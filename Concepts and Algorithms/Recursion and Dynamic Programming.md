### Recursion
1. Recursive solutions, by definition, are built off solutions to sub-problems. Many times, this will mean simply to compute f(n) by adding something, removing something, or otherwise changing the solution for f(n-1). In other cases, you might have to do something more complicated. Following is the method to check whether the recusive function is written correctly. 
	* Recurrence relationship is correct. First assume that the recursive funtion is correct. Then under this assumption, check whether the recurrence relationship is correct. 
	* Base case. We need to have a base case for the recurrence relationship. Otherwise, the recursive function will go to infinite loop. Sometimes, the base case is not clearly written, such as the base case for merget sorting algorithm. 
	* Go back to the base case. When will invoke the recursive function, the function need to go towards the base case. 
If the recursive function satisfies the three above conditions, the recursive function should be correct. If you are still not sure, you can mimic the recursive stack to check the function's correctness. 
	
2. Iterative solutions: recursive algorithms can be very space inefficient. Each recursive call adds a new layer to the stack, which means that if your algorithm has O(n) recursive calls, then it uses O(n) memory. 

	```cpp
	int fib(int i) {
		if (i==0 || i==1) return i;
		return fib(i-1)+fib(i-2);
	}
	```

### Dynamic Programming (DP)
1. Recursive + cached results

	```cpp
	int fibonacci[MAX] = {0};
	int fib(int i) {
		if (i==0 || i==1) return i;
		if (fibonacci[i]!=0) return fibonacci[i];
		fibonacci[i] = fib(i-1) + fib(i-2);
		return fibonacci[i];
	}
	```

#### 1. A child is running up a staircase with n steps, and can hop either 1 step, 2 steps, or 3 steps at a time. Count how many possible ways the child can run up the stairs.
Solution:

1. f(n) = f(n-1) + f(n-2) + f(n-3) 

#### 2. X*Y grids, only go right or up, how many paths from from (0, 0) to (X, Y)?
Solution:

```tex
1. $C_{X+Y}^X=\frac{(X+Y)!}{X!*Y!}$
```
#### 3. A magic index in an array A[0...n-1] is defined as the index such that A[i] = i. Given a sorted array of distinct integers, write a method to find a magic index, if one exists, in array A. (FOLLOW UP, what if the values are not distinct?) 
Solution:

1. Just traverse all index from 0 to n-1, to check which index satisfies A[i]=i.
2. Use binary search. Since the elements are sorted distinct integers, if A[mid]>mid, then the magic index must exists between 0 to mid-1. If A[mid]<mid, then the magic index must exists between mid+1 to n-1. If A[mid]==mid, then we find the magic index. 

Follow UP Solution:

1. Just traverse all index from 0 to n-1, to check which index satisfies A[i]=i.
2. Use binary search. If A[mid]=mid, then we are done and the magic index is mid. Otherwise, the magic index may exist on the left side or the right side of the middle element. We first binary search the left side, then the right side to find the magic index.(Because the integers are not distinct any more, so the magic index may exist on the left side or the right side.)

Note: We assume here that there is only one magic index in the array. 

#### 4. find all the subsets of a set
Solution:

1. Assume there are n elements in the set, a_n is the nth element. A(n) is all the subsets of this set, A(n-1) is all the subsets of the set that consists of the first n-1 elements in the original set, and so on for A(n-2), A(n-3), ..., A(1). Then we have the following recurrence relationship:

	A(n) = {A(n-1), a_n + A(n-1)} 

#### 5. find all the permutations of a string 
Solution:

1. Assume there are n characters in the set, a_n is the nth character. A(n) is all the permutations of this string, A(n-1) is all the permutations of the string that consists of the first n-1 characters in the original string, and so on for A(n-2), A(n-3), ..., A(1). Then we have the following recurrence relationship:

	A(n) = {insert a_n into every possible position of each permutation in A(n-1)}
	
For example, string s = "123". A(2) = {"12", "21"}, then A(3) = {"312", "132", "123", "321", "231", "213"}

### 6. Write an algorithm to print all ways of arranging eight queens on an 8x8 chess board so that none of them share the same row, column or diagonal. In this case, "diagonal" means all diagonals, not just the two that bisect the board.

Solution:

1. Condition on the position of the queen at row 8, then for each possible position of the queen at row 8, condition on the queen at row 7. For every possible position of the queen at row 7, condition on the position of the queen at row 6, and so on for the other queens. See the recurrence formula at page 331.





