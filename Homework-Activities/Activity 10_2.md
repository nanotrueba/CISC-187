# Objective: "Understanding Dijkstra's algorithm" 

### 1. Explain with the help of an example "Why Dijkstra's algorithm fails on negative weights".
Explanation (text):
Dijkstra's algorithm fails on negative weights due to the "greedy principle" which states that once a shortest path to a node is found, it won't reconsider a node. This can eliminate a possibly even shorter path than the path that Dijkstra already stored as the "shortest". Dijkstra assumes that when the algorithm decides that a step is correct, it will not reconsider its decision and continue on with a possibly inefficient path. When we use negative weights in our graph, our path can become much shorter after visiting another node but Dijkstra won't consider it because it has already moved on because it thinks it has found the shortest path.
For example, if Dijkstra reaches a node through a path made up of all positive nodes and finalizes it's "shortest path", it could possibly miss a shorter path that used negative weights. This means that Dijkstra's fails with negative weights because it will falsely deem a path as the "shortest" while a shorter path exist.

#### Example (code):
Our code gives us the output:
"A 0
B 1
C 5
D 3"
But this isn't the actual shortest path to node D because Dijkstra incorrectly finalized it's answer before seeing the negative weight. If we wanted our actual shortest path to D from our source it would be -5. Because 5 - 10 = -5. The part of our function that doesn't handle negative weights are the lines " if current_node in visited: continue". This is the "greedy" principle of the algo because it assumes that once it's removed a node from the priority queue that it has "finalized" the shortest path to the node and will not "revisit" it.
```py
# necessary import for heap fucntions in python
import heapq

# take the graph and the starting source as parameters for our algo
def dijkstras_algo(graph, source):

    # unvisited path nodes 'assume unreachable to start'
    path_length = {node: float('inf') for node in graph}
    path_length[source] = 0
    visited = set()
    # keep min heap to process the node with shortest path next
    heap = [(0, source)]

    while heap:
        current_dist, current_node = heapq.heappop(heap)
        # skip already visited nodes
        if current_node in visited:
            continue
        visited.add(current_node)

# check neighboring nodes for shorter paths
        for neighbor, weight in graph[current_node]:
            if neighbor not in visited:
                dist = current_dist + weight
                # if shorter, push to priority queue
                if dist < path_length[neighbor]:
                    path_length[neighbor] = dist
                    heapq.heappush(heap, (dist, neighbor))

    return path_length

sample_graph = {
    'A': [('B', 1), ('C', 5)],
    'B': [('D', 1)],
    'C': [('D', -10)],
    'D': []
}

result = dijkstras_algo(sample_graph, 'A')
for node, dist in result.items():
    print(node, dist)
    ```
