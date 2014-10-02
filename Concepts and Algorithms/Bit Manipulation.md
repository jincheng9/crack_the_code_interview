## Bit operations
1. AND (&), OR (|), Not (~), XOR (^)
2. Some bit facts and tricks
  * x ^ 0s = x   &nbsp;&nbsp;&nbsp;&nbsp;    x & 0s = 0s    &nbsp;&nbsp;&nbsp;&nbsp;    x | 0s = x
  * x ^ 1s = ~x      &nbsp;&nbsp;&nbsp;&nbsp;   x & 1s = x    &nbsp;&nbsp;&nbsp;&nbsp;    x | 1s = 1s
  * x ^ x = 0s        &nbsp;&nbsp;&nbsp;&nbsp;   x & x = x    &nbsp;&nbsp;&nbsp;&nbsp;     x | x = x
  
## Common bit tasks: get, set, clear, and update bit
1. get: get the ith bit (from the right)

	```C
	bool getBit(int num, int i) {
		return ((num & (1<<i)) != 0);
	}
	```
2. set: set the ith bit 

