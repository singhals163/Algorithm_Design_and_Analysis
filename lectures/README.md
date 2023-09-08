## Important proofs to be done as homework from lecture notes

### Lecture 10
- Find an $O(nlogn)$ time algorithm for Huffman coding (slide 24)
- Write the proof of correctness using the generic technique for a greedy problem for the following problems:
    - Synchronizing the delays in circuits
    - Scheduling jobs to minimize maximum lateness 

### Lecture 11
- Prove the Optimal subpath property (slide 14)
- write a pseudo code for dijkstra (slide 23)
- find the time complexity of dijkstra (slide 23)
- what is the most efficient data structure to efficiently compute the minimum of the unvisited nodes (slide 23)

### Lecture 12
- Write an $O(m+n)$ time algorithm to find the topo sort of a given DAG (slide 22)
    - Can be easily done by maintaining an array which stores the indegree of each node. whenever a node is inserted in the topo sort array, reduce the indegree of its children by 1, if any node now has an indegree 0, insert it into a set and process a node from the set in each iteration
- Does there exist a path consisting of given sequence of nodes in a DAG (slide 30)

### Lecture 13
- Prove the assertion 2 (slide 14)

### Lecture 14
- Write an $O(n^2)$ time algorithm to find if a graph has at most one path from u->v

### Lecture 15
- Design neat, compact and efficient implementation of ***Kosaraju's Algorithm*** (slide 26)
- Optional (Slide 28)