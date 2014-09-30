### 1.1 Implement an alogorithm to determine if a string has all unique characters. What if you cannot use additional
### data structures?

Solution: 
1. Use an array of length 128 to store the number of each character (from 00000000 to 01111111), if there is an element larger
than 1, then this string doesn't have all unique characters. (O(n)) 

2. If we cannot use additional data structrures, then we can use a double for-loop to compare the characters in 
the string, if there exists the same character, then the string doesn't have all unique characters. (O(n^2))

or we can sort the characters in the string, and then traverse all characters to compare the neighbouring characters. (O(nlg(n)))

1.2 Implement a function void reverse(char* str) in C or C++ which reverses a null terminated string.
==========
Solution:
1. First get the length of the string, say n, and then exchange the characters 0<->n-1, 1<->n-2, ...

1.3 Given two strings, write a method to decide if one is a permutation of the other.
==========
Solution:
1. Compute the number of each character for each string. If the number of each character
is the same between two strings, then one is a permutation of the other.

1.4 Write a method to replace all spaces in a string with '%20'
==========
Solution:
First, count the number of spaces, then we know the length of the new string. Then we can 
1. Create a new string, and traverse the old string, if it's not a space, keep the original character in the 
new string, otherwise, replace the space with '%20'. 
2. Extend the length of the old string, then edit the string backwards. Thus we don't need to create a new string.

1.5 Implement a method to perform basic string compression usign the counts of repeated characters. Like 
aabcccccaaa -> a2b1c5a3. If the compressed string would not become smaller then the original string, just
return the original string. 
==========
Solution:
1. Use another string to represent the compressed string, then compare the length of two strings, return 
the string with smaller length. If they have the same length, return the original string. As regard to how
to obtain the compressed string, we traverse from the first character of the original string, add this character
to the new string, and count the consecutive number of this character, and then add another character to 
the new string, count the corresponding number, etc. (In C++, we can use the operator + to concatenate strings.) 

1.6 Rotate a NxN matrix by 90 degree
==========
Solution:
1. Rotate for each layer, can either from the outlayer to inner layer, or inner to outer.

1.7 Write an algorithm such that if an element in an MxN matrix is 0, its entire row and column are set to 0
==========
Solution:
1. Copy the original matrix as M', and then traverse the elements in M', if the element is 0, then the 
corresponding rows and columns in the original matrix are set to 0.
2. First traverse the original matrix to mark the rows and columns that need to be set to 0, and then use 
the mark array to set the corresponding rows and columns to 0.

1.8 Assume you have a method isSubstring which checks if one word is a substring of another. Given two
strings s1 and s2, write code to check if s2 is a rotation of s1 using only one call to isSubstring (
e.g. "waterbottle" is a rotation of "erbottlewat").
==========
Solution:
1. Let s3 = s1+s1, if s2 is a substring of s3, then s2 is a rotation of s1.





