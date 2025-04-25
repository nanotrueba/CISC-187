# Objective: "Understanding Dijkstra's algorithm" 

### 1. Explain with the help of an example "Why Dijkstra's algorithm fails on negative weights".
Explanation (text):
Dijkstra's algorithm fails on negative weights due to the "greedy principle" which states that once a shortest path to a node is found, it won't reconsider a node. This can eliminate a possibly even shorter path than the path that Dijkstra already stored as the "shortest". Dijkstra assumes that when the algorithm decides that a step is correct, it will not reconsider its decision and continue on with a possibly inefficient path. When we use negative weights in our graph, our path can become much shorter after visiting another node but Dijkstra won't consider it because it has already moved on because it thinks it has found the shortest path.
For example, if Dijkstra reaches a node through a path made up of all positive nodes and finalizes it's "shortest path", it could possibly miss a shorter path that used negative weights. This means that Dijkstra's fails with negative weights because it will falsely deem a path as the "shortest" while a shorter path exist.

#### Example (code):

