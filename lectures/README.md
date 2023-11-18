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


### Lecture 27
- Proof of edge disjoint paths

###  Lecture 28
- What if we used the longest suffix of 1's as the as $\phi$ (slide 27)

### Lecture 29
- How to work with the credits based approach?
- Slide 29, can we take $Size(T)$ as the amortised cost?
    <br>Ans: No, because the initial cost will not be 0 in that case. We can still use it by using the initial cost in the final analysis of the amortised cost, but such kind of potential functions are not studied in the class
- Exercises (Slide 34)


### Topics to revisit
- lectures complete(done, except finding median last lecture)
- amortised sheet (done)
- how to calculate pi function for KMP (done, same as KMP) (visit other problems on KMP again)
- remaining sheet problems 
- min perimeter triangle (done)
- proof of min flow (done)
- assignments 
- max-min flow book important problems (done)
- problems on other domains if time permits
- proof of topo sort
- non-integral max flow termination
