The key observation is hidden in the note:

You are allowed to revisit cities and roads.

This completely changes the problem.

Important Insight

Since you can travel back and forth as much as you want, any road inside the connected component containing city 1 and city n can be included in your path.

So instead of finding the "best path", we only need to find:

The minimum edge weight among all roads in the connected component that contains city 1.

Why?

There is guaranteed to be a path from 1 to n.
If an edge belongs to the same connected component, you can always detour to use that edge and then continue toward n.
Therefore the smallest edge in that component is achievable as the path score.
Algorithm (DFS/BFS)
Build an adjacency list.
Start DFS/BFS from city 1.
Visit every reachable city.
While traversing, keep updating the minimum road distance seen.
Return that minimum.

Time Complexity:

O(n + m)

Space Complexity:

O(n + m)

where m = roads.length.
