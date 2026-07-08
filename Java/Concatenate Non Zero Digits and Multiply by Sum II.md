The solution first scans the string and stores the positions and values of all non-zero digits while building a prefix sum array of their values. For each query, it uses binary search to quickly locate the non-zero digits that fall within the specified substring, avoiding unnecessary processing of zeros. It then reconstructs the number x by concatenating those non-zero digits modulo 10
9
+7, computes the sum of the digits using the prefix sum array, and multiplies the two values to produce the final answer modulo 10
9
+7. This approach reduces unnecessary work by ignoring zero digits and efficiently locating the required range for each query.
