# Number of Substrings

Let's generate every substring of the string s and observe the properties of the substrings that contain all three characters (valid substrings).


Since we only care about the existence of at least one occurrence of each character, we only track the last index position where it was last seen.

As we observed, the character with the minimum index (min 
idx
​
 ) is the limiting factor for the current iteration.

Any valid substring ending at the current index (i) must start at index 0 and ends at min 
idx


Therefore, the count of valid substrings for the current iteration is
(min 
idx
​
 −0+1), or:
count=min 
idx
​
 +1
​
 
We simply add the count contribution to the total result at every iteration.

Time Complexity: O(n)
Space Complexity: O(1)

