{% from "components/pdf.njk" import pdf %}
{% set title="Assignment 7" %}
{% set file="assignment06.pdf" %}

<frontmatter>
title: {{title}}
</frontmatter>

# {{title}}

{{ pdf(file, "assignments") }}

# Question 1

This is a variation of the knapsack problem. Observe that each element could be
in either set X or set Y, giving rise to the idea that we can use a recursion
where in each function, we take the minimum between putting current element
$A[i]$ in set X or set Y.

taking the top down approach,

```psudocode
class Solution:
  int[n][nM] memo
  int sum

  function minDiff(A)
    initialise memo to -1
    sum <- sum of elements in A
    return helper(len(A) - 1, sumX)

  function helper(i, sumX)
    if (memo[i][sumX] != -1)
      return memo[i][sumX]
    
    if (i < 0)
      memo[i][sumX] <- abs(sumX - 2 * (sum - sumX))
      return memo[i][sumX]

    memo[i][sumX] <- min(helper(i - 1, sumX + A[i]), helper(i - 1, sumX))
    return memo[i][sumX]
```

Since there are at most $n * n \cdot M = n^2 M$ possible states, the time
and space complexity of this algorithm are $O(n^2\cdot M)$.

Note that using bottom up approach, we can reduce the space complexity to
$O(n\cdot M)$ by only

# Question 2

## Basic recursion

```pseudocode
fun maxNonAdj(A, n)
  if (n < 0)
    return 0
  if (n == 0)
    return A[0]

  // third case is for when the current element is negative
  return max(maxNonAdj(A, n - 1), A[n] + maxNonAdj(A, n - 2), maxNonAdj(A, n - 2))
```

## Bottom up approach

```pseudocode
fun maxNonAdj(A, n)
  int[n] dp
  dp[0] <- A[0]
  for i in range(1, n)
    twoago <- i - 2 >= 0 ? dp[i - 2] : 0
    dp[i] <- max(dp[i - 1], A[i] + twoago, twoago)
  
  return dp[n - 1]
```

<box header="Correctness" type="info">

At each step, there's two cases:  

- current element is positive: we can either take it or not take it, and we take
  the maximum of the two
- current element is negative: we do not considering taking it, and we take the
  maximum of the sum including previous elemtent and the sum excluding previous
  element

</box>

<box header="Time and space complexity" type="info">

The time complexity of this algorithm is $O(n)$ since we only need to iterate
through the array once. The space complexity is also $O(n)$ since we need to store
the maximum sum of non-adjacent elements up to each index in the dp array.
However, we can optimize the space complexity to $O(1)$ by only keeping track of
the maximum sums for the previous two indices instead of the entire dp array.
</box>

```pseudocode
fun maxNonAdj(A, n)
  int[2] dp
  dp[0] <- A[0]
  for i in range(1, n)
    twoago <- i - 2 >= 0 ? dp[0] : 0
    val <- max(dp[1], A[i] + twoago, twoago)
    dp[0] <- dp[1]
    dp[1] <- val
  
  return val
```
