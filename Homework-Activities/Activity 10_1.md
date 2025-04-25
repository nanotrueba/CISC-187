# Objective: "Implement Breadth-first search and Depth-first search algorithms in C++"
### 1. Create a theoretical graph using a pen and paper OR electronically.
![JPEG image-4213-A20A-97-0](https://github.com/user-attachments/assets/f0dfab10-9dad-40d7-a5e6-fa93250849bd)
### 2. Implement the graph created in step 1 and apply breadth and depth-first search algorithms using C++.
```cpp
// necessary imports for building dfs and bfs
#include <iostream>
#include <vector>
#include <queue>
#include <stack>
using namespace std;

// create graph class
class Graph {
    vector<char> nodes;
    vector<vector<char>> graph;

// add node features
public:
    void add(char label) {
        nodes.push_back(label);
        graph.push_back({});
    }

    void add(char from, char to) {
        int i = indexOf(from);
        graph[i].push_back(to);
    }

    // bfs algo implemented using pseudocode and logic from the lecture
    void bfs(char start) {
        vector<bool> visited(nodes.size(), false);
        queue<char> q; //queue is unique to bfs

        visited[indexOf(start)] = true;
        q.push(start);

        cout << "BFS: ";
        while (!q.empty()) {
            char temp = q.front();
            q.pop();
            cout << temp << " ";

            for (char neighbor : graph[indexOf(temp)]) {
                int ni = indexOf(neighbor);
                if (!visited[ni]) {
                    visited[ni] = true;
                    q.push(neighbor);
                }
            }
        }
        cout << endl;
    }

    // dfs algo implemented using pseudocode and logic from the lecture
    void dfs(char start) {
        vector<bool> visited(nodes.size(), false);
        stack<char> s; //stack is used for dfs

        s.push(start); //push start node to stack

        cout << "DFS: ";
        while (!s.empty()) {
            char curr = s.top();
            s.pop();

            int idx = indexOf(curr);
            if (!visited[idx]) {
                visited[idx] = true; 
                cout << curr << " ";

                for (char neighbor : graph[idx]) {
                    int ni = indexOf(neighbor);
                    if (!visited[ni]) {
                        s.push(neighbor);
                    }
                }
            }
        }
        cout << endl;
    }

    int indexOf(char label) {
        for (int i = 0; i < nodes.size(); ++i) {
            if (nodes[i] == label) return i;
        }

    }
};

int main() {
// initialize graph
    Graph g;

    // create sample graph
    g.add('A');
    g.add('B');
    g.add('C');
    g.add('D');
    g.add('E');
    g.add('F');
    g.add('A', 'B');
    g.add('A', 'C');
    g.add('B', 'D');
    g.add('B', 'E');
    g.add('C', 'F');

    // run algos
    g.bfs('A');
    g.dfs('A');

    return 0;
}
```
### 3. Compare both search algorithms in the context of Big O notations.
Both BFS and DFS have the same time complexity that is dependent on the number of vertices and edges in the graph. The time complexity can be described as O(V+E) or very roughly O(N) if we consider N to be the number of input size. In more dense graphs, this is closer to O(N^2), it just depends on if the graph is sparse or dense. BFS uses a queue and is better for finding the shortest path in unweighted graphs. DFS on the other hand, uses a stack and is more efficient in deep and narrow graphs. In short, they both share O(V+E) time complexity but BFS is better for unweighted graphs and DFS is slightly less optimal but useful for cases like patern detection, exploring all possible paths and very deep but narrow graphs.
