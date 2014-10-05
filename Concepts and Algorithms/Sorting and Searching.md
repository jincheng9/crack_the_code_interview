Some Useful References from Wikipedia: http://zh.wikipedia.org/wiki/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95#.E7.A9.A9.E5.AE.9A.E7.9A.84.E6.8E.92.E5.BA.8F

## Sorting Algorithms
#### Bubble Sort | Runtime: O(n^2) average and worst case. Memory: O(1)
1. Why O(n^2)? at least compare O(n^2) times

#### Selection Sort | Runtime: O(n^2) average and worst case. Memory: O(1)
1. Why O(n^2)? at least compare O(n^2) times
2. Find the smallest element using a linear scan and swap it with the first element. If the first element is the smallest element, do not need to swap. Then find the second smallest and swap it with the second element. If the second element is the second smallest, do not need to swap. Continue doing this until the array is sorted.

#### Merge Sort | Runtime: O(nlogn) average and worst case. Memory: Depends
1. Recurrsive Method, Divide and Conquer

	```cpp
	void mergeSort(int *array, int low, int high) {
		if (low < high) {
			int mid = (low+high)/2;
			mergeSort(array, low, mid);
			mergeSort(array, mid+1, high);
			merge(array, low, mid, high);
		}
	}
	```

#### Quick Sort | Runtime: O(nlogn) average, O(n^2) worst case. Memory: O(logn)
1. Recursive Method, Divide and Conquer

	```cpp
	void quickSort(int *array, int low, int high) {
		int index = partition(array, low, high);
		if(low < index-1) {
			quickSort(array, low, index-1);
		}
		if(index < right) {
			quickSort(array, index, right);
		}
	}
	```

#### Radix Sort | Runtime: O(kn)


## Searching Algorithms
#### Binary Search
1. Recursive version of binary search

	```cpp
	int binSearch(int *array, int value, int low, int high) {
		int mid = (low+high)/2;
		if(array[mid]==value) {
			return mid;
		} else if(array[mid]>value) {
			return binSearch(array, value, low, mid-1);
		} else {
			return binSearch(array, value, mid+1, high);
		}
	}
	```
	
2. Iterative version of binary search

	```cpp
	int binSearch(int *array, int value, int low, int high) {
		while(low<=high) {
			int mid = (low+high)/2;
			if(array[mid] == value) {
				return mid;
			} else if(array[mid] > value) {
				high = mid - 1;
			} else {
				low = mid + 1;
			}
		}
	}
	```
	

