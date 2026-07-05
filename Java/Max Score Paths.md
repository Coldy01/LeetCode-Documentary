Although the problem says

Start at S (bottom-right)
End at E (top-left)

it is much easier to think in reverse.

Imagine we start from E and move

Down
Right
Down-right

instead.

This is exactly equivalent because every path can simply be reversed.

DP State

For every cell (i,j) maintain

score[i][j] = maximum score from E to (i,j)

ways[i][j] = number of maximum-score paths to (i,j)

Initially every score is

-1

meaning unreachable.

Base Case

At E

score[0][0] = 0
ways[0][0] = 1

because we start there and have collected nothing.

Transition

Suppose we're computing

(i,j)

We may come from

(i-1,j)
(i,j-1)
(i-1,j-1)

because those correspond to

down
right
diagonal

in the original direction.
