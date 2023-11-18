## Solutions to practice problems

### 1. Flow Fundamentals
- You will have to do a bfs/dfs in order to find a path from source to sink, only 1 such path exists
- If the edge was already present in the residual graph of network, adding 1 unit won't affect anything coz the edge will not be included in the min-cut
- If the edge belonged to nodes present in different sets, adding it will lead to a path connecting $A$ and $\bar A$
- Finding this path will take $O(n+m)$ time coz it is just one in number. Once done, increase the flow along the path by one unit and the answer will be the required answer


### 3. Mobile phones and base stations
- Form a bipartite graph with suitable matching using range constraints
- tower to sink L edge capacities
- source to tower 1 edge capacities
- all other edges 1 edge capacity

### 4. Max-damage to the network
- In the directed graph, find max flow
- Find all unique edge paths in the max flow, and for each path, choose any edge, and mark its capacity as 0, or delete the edge
- If the number of unique paths are less than k, you may choose multiple edges from some paths after deleting at least 1 edge from each path
- If the number of unique paths is greater than or equal to k, choose any k unique paths and delete 1 edge from each path

### 5. Unique min-cut
- Apart from A, find another set B, whose nodes have a path to t
- If V/{AUB} is not an empty set, there may exist multiple min cuts

### 6. Vertex disjoint paths
- split each vertex into two vertex $v_{in}$ and $v_{out}$, and make an edge connecting the two vertices of capacity 1

### 7. 


