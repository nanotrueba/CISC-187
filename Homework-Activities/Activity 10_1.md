# Objective: "Implement Breadth-first search and Depth-first search algorithms in C++"
![JPEG image-4BD1-8C52-29-0](https://github.com/user-attachments/assets/5d4b7ab2-5747-47a1-87e9-10a73a399a62)

### 1. Create a theoretical graph using a pen and paper OR electronically.

### 2. Implement the graph created in step 1 and apply breadth and depth-first search algorithms using C++.

### 3. Compare both search algorithms in the context of Big O notations.
Both BFS and DFS have the same time complexity that is dependent on the number of vertices and edges in the graph. The time complexity can be described as O(V+E) or very roughly O(N) if we consider N to be the number of input size. In more dense graphs, this is closer to O(N^2), it just depends on if the graph is sparse or dense. BFS uses a queue and is better for finding the shortest path in unweighted graphs. DFS on the other hand, uses a stack and is more efficient in deep and narrow graphs. In short, they both share O(V+E) time complexity but BFS is better for unweighted graphs and DFS is slightly less optimal but useful for cases like patern detection, exploring all possible paths and very deep but narrow graphs.
