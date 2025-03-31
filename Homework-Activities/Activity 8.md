# 1. Diagram showing what the binary search tree would look like
![IMG_0691](https://github.com/user-attachments/assets/04f23381-ffe3-4374-958e-371132551e56)

# 2. If a well-balanced search tree contained 1000 values, what is the maximum number of steps it would take to search for a value within it?
log (base 2) (1000) = 9.97 which is 10 steps.
# 3. Write an algorithm that finds the greatest value within a binary tree.
```py
class Tree_Node:
    def __init__(self, value=0, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def find_max(root):
    while root and root.right:
        root = root.right
    return root.value if root else None

root = Tree_Node(10)
root.left = Tree_Node(1)
root.right = Tree_Node(2)
root.right.right = Tree_Node(3)

print("Greatest value:", find_max(root))  

```
# 4. Write code in C++ that implements the task from #1. Only insertion operations are required.
```cpp
#include <iostream>
using namespace std;

class Tree_Node {
    int val;
    Tree_Node* left;
    Tree_Node* right;

    Tree_Node(int x) : val(x), left(nullptr), right(nullptr) {}
};

Tree_Node* insert(Tree_Node* root, int val) {
    if (root == nullptr) {
        return new Tree_Node(val);
    }

    if (val < root->val) {
        root->left = insert(root->left, val);
```
