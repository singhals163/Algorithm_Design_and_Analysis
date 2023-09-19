## Solution to the practice problems

### Q1. Monotonically increasing subsequence
- Recursive formulation:
    Let $T[i]$ store the maximum number of elements that can lie in the largest such subsequence such that $i^{th}$ element is included in the subsequence.<br>
- $T[i] = 1$ <br>
    $\forall\ j < i,\ if\ a_i >= a_j $ <br>
    $ T[i] = max(T[i], T[j]+1)$
- Update the parent of $i$ to $j$ for which $T[i]$ is maximum.
