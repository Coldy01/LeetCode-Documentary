Step 1: Multi-source BFS
Put all thief cells into the queue initially.
Run BFS to compute the minimum Manhattan distance to any thief for every cell.
dist[i][j] becomes the safeness value of that cell.

Example:

Grid
0 0 1
0 0 0
0 0 0

Distance
2 1 0
3 2 1
4 3 2
Step 2: Maximum Safeness Path

Now each cell has a value (dist).

We need a path where the minimum value along the path is as large as possible.

Instead of minimizing cost like Dijkstra, we maximize:

pathSafeness = min(currentSafeness, dist[next])

A max heap always explores the path with the highest current safeness first.

When we first reach (n-1,n-1), that safeness is guaranteed to be optimal.
