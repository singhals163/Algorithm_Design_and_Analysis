## Solutions to the practice problems

### Placing mobile towers

### 4. Scheduling jobs on PCs and a Supercomputer
Sort in non-decreasing order according to the finish time on PC

### 5. Scheduling to Maximise happiness
Sort the customers in non-decreasing order $\frac{t_i}{w_i}$

### 7. Time Varying MST
Check the MST only at t1 and t2. Divide the edges into 4 types: 
1. both included before implies both included after
2. none included before implies none included after
3. upper included before implies lower included after
4. lower included before 
    1. upper included after(coz lower was not eliminating upper one)
    2. lower included after(coz lower was eliminating upper one)
5. only in d2, the weight of MST will change.
6. This forms a convex upper hull and thus one only needs to check at the start and end of the time.

### 8. Maximum Capacity Path
$dist[v] = 0\ \forall\ v \in\ V$ <br>
$dist[s] = \infty $ <br>
$visited[s] = false\ \forall\ v\ \in\ V$ <br>
$visited[s] = false\ \forall\ v\ \in\ V$ <br>
$max\_heap\ p $ <br>
$p.push(\{dist[s], s\}) $ <br>
$while(\ !p.empty()\ )\ \{$ <br>
$\ \ \ \ \ \ curr = p.top()$ <br>
$\ \ \ \ \ \ p.pop()$ <br>
$\ \ \ \ \ \ if\ (\ visited[curr]\ )\ continue;$ <br>
$\ \ \ \ \ \ visited[curr] = true;$ <br>
$\ \ \ \ \ \ for(curr, v) \in E\ \{$ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ if\ (\ !visited[v]\ )\ \{$ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ if(dist[v] < min (dist[curr], C(curr, v)))\ \{$ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ dist[v] = min(dist[curr], C(curr, v))$ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ p.push(\{dist[v], v\}) $ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \}$ <br>
$\ \ \ \ \ \ \ \ \ \ \ \ \}$ <br>
$\ \ \ \ \ \ \}$ <br>
$\}$ <br>

### 10. Special Shortest Paths
- Find the BFS order traversal of all nodes starting from the root node
- Traverse all the nodes in the found order
- for each node in BFS traversal: $degree[v] \rightarrow$ depth of $v$ in dfs tree
- $dist[v] = \infty\ \forall\ v\ \in V$  
- traverse in increasing order of degree.
- $dist[0] = 0$
- for each node $v$ in BFS:
    - for each edge $(u, v) \in E$ with $degree[u] = degree[v] - 1$
        - $dist[v] = \min(dist[v], dist[u] + w(u, v))$
- Time : $2\cdot O(n+m) \approx O(n+m)$