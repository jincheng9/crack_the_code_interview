## Bit operations
1. AND (&), OR (|), Not (~), XOR (^)
2. Some bit facts and tricks
  * x ^ 0s = x          x & 0s = 0s        x | 0s = x
  * x ^ 1s = ~x         x & 1s = x        x | 1s = 1s
  * x ^ x = 0s           x & x = x         x | x = x
  
## Common bit tasks: get, set, clear, and update bit
1. get: get the ith bit (from the right)
	```C
	bool getBit(int num, int i) {
		return ((num & (1<<i)) != 0);
	}
	```

