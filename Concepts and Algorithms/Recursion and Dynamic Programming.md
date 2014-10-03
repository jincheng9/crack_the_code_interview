### Recursion
1. Recursive solutions, by definition, are built off solutions to sub-problems. Many times, this will mean simply to compute f(n) by adding something, removing something, or otherwise changing the solution for f(n-1). In other cases, you might have to do something more complicated. 
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
1. C(X+Y, X) $C_{X+Y}^X$
```
#### 3. find magic index, A[i] = i

#### 4. find all the subsets of a set

#### 5. find all the permutations of a string 



