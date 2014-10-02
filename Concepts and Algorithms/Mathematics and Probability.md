### Basic concepts in mathematics and probability
1. Prime numbers
	* all positive integers can be decomposed into a product of primes. 
	* gcd(x, y) * lcm(x, y) = x*y
	* check for primality of integer n 
		* check 2, 3, ..., n-1
		* check 2, 3, ..., sqrt(n)
		* cross off the number divisible by 2, then 3, 5, 7, ...
2. Probability
	* P(A and B) = P(B|A)P(A)
	* P(A or B) = P(A) + P(B) - P(A and B)
	* diffference between independence and mutual exclusivity
		* independence: P(A and B) = P(A) * P(B)
		* mutual exclusivity: P(A and B) = 0

#### 1. Given a two-dimensional graph with points on it, find a line which passes the most number of points.
Solution:

1. Assume we have n points, then we can have n*(n-1)/2 lines. Hash these lines, then see which line is the most common line. 

#### 2. Find the kth number such that the only prime factors are 3, 5, and 7.
Solution:

1. The pseudocode is as follows:
	1. Initialize array and queues Q3, Q5, and Q7
	2. Insert 1 into array. (1 is the first element)
	3. Insert 1*3, 1*5, and 1*7 into Q3, Q5, and Q7 respectively.
	4. Let x be the minimum element in Q3, Q5 and Q7. Append x to magic.
	5. If x was found in:
		* Q3 -> append x*3, x*5, and x*7 to Q3, Q5, and Q7 respectively. Remove x from Q3.
		* Q5 -> append x*5, and x*7 to Q5 and Q7 respectively. Remove x from Q5.
		* Q7 -> append x*7 to Q7. Remove x from Q7
	6. Repeat steps iv-vi until we found k elements. 


 