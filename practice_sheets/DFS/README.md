## Solutions to practice problems

### 1. The classification of edges
1. Yes
2. No, there needs to exist another path $u\rightarrow v$ in which case dfs traversal might visit this path first and thus $(u, v)$ becomes a forward edge in this case. If no other path exist, invoking a dfs traversal from u will always add the edge $(u, v)$ as a tree edge
3. No, for this to happen $dfs(v)$ should invoke $dfs(u)$ in later calls which might not be the case always
4. No, for this to happen $dfs(v)$ should not invoke $dfs(u)$, i.e. $u$ shouldn't exist in the dfs tree from v, which might not be the case always

### 2. More on DFS
1. True <br>
    Prove it using the property that when $dfs(u)$ is invoked, we can remove all the visited nodes till then and v will lie in the dfs tree coz there is a path $u\rightarrow v$ coz $u$ and $v$ are strongly connected components. Although if $dfs(v)$ is invoked earlier the case will be reserved and thus $v$ will become the ancestor of $u$ in this case 
2. False <br>
    Note: if there is a path $u \rightarrow v$ in the graph, there can't be a path $v \rightarrow u$ in the graph coz in this case the graph will contain a cycle. Invoking $dfs(v)$ will only grow in the right side in topo sort and will never contain the node u. Now, invoking $dfs(u)$ will not include the v in the dfs tree of u, thus u can't be the ancestor of v in this case.
3. False <br>
    Nothing can be said about $F(w) ? F(v)$
    1. If we invoke a $dfs(v)$ then $F(w) > F(v)$
    2. if we invoke a $dfs(u)$ then the dfs may first go to $v$ or $w$. if it goes to w first and there is no edge from w to v then, $F(w) < F(v)$. <br>
    Note: we can surely say that $F(u) > F(v)$
4. True
```
            A
              .
           / \\
          .  .
          B---C
```
$dfs(B)\rightarrow B-C-A$ <br>
$dfs(A)\rightarrow A-C, A-B$

### 3. About SCCs in a graph
Counterexample: 

Two cycles combined together int the form of infinity will form a SCC but they will contain two separate cycles and not one

### 4. Least toll tax path
1. Find the SCC of the graph G. ----------------------------- $O(n+m)$
2. Find the component to which $s$ belongs ------------ $O(1)$
3. Find the component to which $t$ belongs ------------ $O(1)$
4. Create a DAG of the SCCs using the adjacency matrix of size equal to the number of SCCs in the graph
5. Sort the nodes in the topo sort
6. find the min distance from $s$ to $t$ by moving from left to right in the topo sort array

### 5. Least Label Vertex
Note: If the graph has back edges present, then we can't make use of DFS to find the least vertex in a graph. Thus we proceed with the following steps:

1. Sort the graph according to the finish time of DFS traversal.
2. Use this to find the SCCs in the graph
3. Create a new graph of size equal to the number of SCCs in the graph
4. Assign the label of each node in the SCC graph as the least label of nodes belonging to that SCC component: This can be done $O(n)$ time.
5. The created SCC graph is a DAG and thus have a topological ordering. Finding which takes at max $O(n+m)$ time coz the SCC graph is at max the size of the original graph
6. Traverse the topo sort array from right to left and assign the least label using DP in $O(n+m)$ time.
7. Use these new labels to assign $L(v)$ as the label of all the vertices belonging to that strongly connected component

### 6. Semi-connected graphs

>Question: Is a stongly connected graph also semi-connected, can $(u,v)$ both have paths to each other in a semi connected graph?<br>
Ans: 
1. The graph cannot contain cycles, because if it does, there will be a pair of nodes $(u,v)$ such that $u\rightarrow v$ and $v\rightarrow u$
2. If the graph can't contain cycle, it is a DAG and thus can have a topological ordering.  $O(n+m)$  time
3. In the topological ordering, there must be an edge $(i, i+1)$ $\forall\ i \in n$. Because if there is no edge $(i, i+1)$. and there can't be an edge $(i+1, i)$ (because the graph is a DAG), then the graph is not semi-connected as there is no edge between $i$ and $i+1$
4. Check if there exist an edge $(i, i+1)\ \forall\ i \in n$ in the topo sort array. $O(n)$ time

[Stack Overflow solution](https://stackoverflow.com/questions/30642383/determine-if-a-graph-is-semi-connected-or-not)

Note: My first statement is wrong because in semi-connected graphs either one node is reachable from the other or both are mutually reachable. Therefore making the SCC graph of the given graph which is a DAG leads us to step3

Haffun :)