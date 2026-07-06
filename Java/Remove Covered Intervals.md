Key Observation

Suppose the intervals are sorted by:

Left endpoint in ascending order
If left endpoints are equal, right endpoint in descending order

Example:

[1,4], [1,3], [2,8], [3,6]

becomes

[1,4], [1,3], [2,8], [3,6]

Notice that when two intervals start at the same point, the longer one comes first.

Why this sorting?

Consider:

[1,4]
[1,3]

If we sorted the second value ascending:

[1,3]
[1,4]

then we'd incorrectly think [1,4] is not covered.

Sorting by descending right endpoint ensures the covering interval appears first.

Algorithm

Maintain

maxEnd = farthest right endpoint seen so far
count = remaining intervals

For each interval after sorting:

if end <= maxEnd
    covered
else
    count++
    maxEnd = end

Why?

Because every previous interval starts no later than the current one.

If its end is also larger,

previous.start <= current.start
previous.end >= current.end

which exactly matches the definition of coverage.

Example 1

Input

[[1,4],[3,6],[2,8]]

Sorted

[1,4]
[2,8]
[3,6]

Process:

maxEnd = -1

[1,4]
4>-1
count=1
maxEnd=4

[2,8]
8>4
count=2
maxEnd=8

[3,6]
6<=8
covered

Answer

2
Example 2

Input

[[1,4],[2,3]]

Sorted

[1,4]
[2,3]

Process

maxEnd=4

[2,3]
3<=4
covered

Answer

1
