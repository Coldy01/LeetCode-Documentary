for any element we have three options:
either take it into seq1
or take it into seq2
ignore it
at any point we do not care about the elements in seq1 and seq2, we only need gcd of seq1 and seq2.
so our state will be (i,g1,g2) where i is the index, g1 is gcd of seq1 and g2 is gcd of seq2
transition
lets say our current number is x=nums[i]
ignore current number, so g1 and g2 will ot change (idx+1,g1,g2)
put in seq1, so we will find the new gcd of seq1 say ng1, then (idx+1, ng1, g2)
put in seq2, so we find new gcd for seq2 say ng2 and then we call (idx+1,g1, ng2)
base case
when all elements are processed, then we want g1 == g2 and also we want that the sequence should be non-empty so g1>0 and g2>0
so this is the recursion + memoization approach.
then we convert this into iterative 3d dp
and then in iterative 3d dp we noticed that state i+1 depends on previous layer only
so no need to store all n+1 layers, so we space optimize the 3d dp solution
we replace dp[i] with cur and dp[i+1] with next
