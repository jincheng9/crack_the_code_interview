## Bit operations
1. AND (&), OR (|), Not (~), XOR (^)
2. Some bit facts and tricks
  * x ^ 0s = x        &nbsp;&nbsp;&nbsp;&nbsp;    x & 0s = 0s    &nbsp;&nbsp;&nbsp;&nbsp;    x | 0s = x
  * x ^ 1s = ~x       &nbsp;&nbsp;&nbsp;&nbsp;    x & 1s = x     &nbsp;&nbsp;&nbsp;&nbsp;    x | 1s = 1s
  * x ^ x = 0s        &nbsp;&nbsp;&nbsp;&nbsp;    x & x = x      &nbsp;&nbsp;&nbsp;&nbsp;    x | x = x
  
## Common bit tasks: get, set, clear, and update bit

The ith bit means that the rightmost bit as the 0th bit, count from right to left. 

1. get: get the ith bit (from the right) 

	```cpp
	bool getBit(int num, int i) {
		return ((num & (1 << i)) != 0);
	}
	```
2. set: set the ith bit to be 1
	
	```cpp
	int setBit(int num, int i) {
		return num | (1 << i);
	}
	```
3. clear: clear the ith bit, i.e., let the ith bit be 0

	```cpp
	int clearBit(int num, int i) {
		return num & (~(1 << i));
	}
	```
4. update: update the ith bit to be v, if v is 1, then the ith bit will be 1, otherwise 0
	
	```cpp
	int updateBit(int num, int i, int v) {
		int mask = ~(1<<i);
		return (num & mask) | (v << i);
	}
	```
### 5.4 Explain what the following code does: ((n & (n-1)) == 0).
Solution:

1. if ((n & (n-1)) == 0), then n is a power of 2 or n is 0. 

	