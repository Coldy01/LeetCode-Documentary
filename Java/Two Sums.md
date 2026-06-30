# Two Sums 

The solution uses a hash table to achieve linear time complexity. Here's how the implementation works step by step:

We initialize an empty dictionary d to store the numbers we've seen along with their indices. The key will be the number itself, and the value will be its index in the array.

We iterate through the array using enumerate(nums) to get both the index i and the value x at each position:

Calculate the complement: For the current number x, we calculate y = target - x. This is the value we need to find to make the sum equal to target.

Check if complement exists: We check if y is already in our dictionary d. If it exists, it means we've previously encountered a number that, when added to our current number x, equals the target.

Return the result: If we find y in the dictionary, we immediately return [d[y], i], where d[y] is the index of the complement we stored earlier, and i is the current index.

Store current number: If the complement is not found, we store the current number and its index in the dictionary as d[x] = i. This allows future iterations to find this number as a potential complement.

The algorithm guarantees we'll find the answer in a single pass because:

When we encounter the first number of the pair, we store it
When we encounter the second number of the pair, we'll find the first one already stored in the hash table
The problem guarantees exactly one solution exists
Time Complexity: O(n) - we traverse the array once Space Complexity: O(n) - in the worst case, we might store almost all elements in the hash table before finding the pair
