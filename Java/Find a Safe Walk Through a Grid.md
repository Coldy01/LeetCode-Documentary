This problem can be solved using Dijkstra's algorithm (or a priority queue BFS).

Key Idea
Treat each cell as a node.
Moving into a cell with 1 costs 1 health.
Moving into a cell with 0 costs 0 health.
We want to minimize the total health lost from (0,0) to (m-1,n-1).

If the minimum health lost is less than health, then the remaining health is at least 1.

Since:

Initial health = health
Remaining health = health - damage
Need remaining health ≥ 1

So:

damage <= health - 1

or equivalently

damage < health
