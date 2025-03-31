# 1. Diagram showing what the binary search tree would look like
![IMG_0691](https://github.com/user-attachments/assets/04f23381-ffe3-4374-958e-371132551e56)

# 2. If a well-balanced search tree contained 1000 values, what is the maximum number of steps it would take to search for a value within it?
log (base 2) (1000) = 9.97 which is 10 steps.
# 3. Write an algorithm that finds the greatest value within a binary tree.
```
class TreeNode:
    def __init__(self, value=0, left=None, right=None):
        self.value = value
        self.left = left
        self.right = right

def find_max(root):
    # Traverse to the rightmost node
    while root and root.right:
        root = root.right
    return root.value if root else None

# Example Usage
root = TreeNode(10)
root.left = TreeNode(5)
root.right = TreeNode(15)
root.right.right = TreeNode(20)

print("Greatest value:", find_max(root))  # Output will be 20

```
# 4. Write code in C++ that implements the task from #1. Only insertion operations are required.
```
#include <iostream>
using namespace std;

// Definition of a TreeNode
struct TreeNode {
    int value;
    TreeNode* left;
    TreeNode* right;

    TreeNode(int x) : value(x), left(nullptr), right(nullptr) {}
};

// Function to insert a new value into the BST
TreeNode* insert(TreeNode* root, int value) {
    // If the tree is empty, return a new node
    if (root == nullptr) {
        return new TreeNode(value);
    }

    // Otherwise, recur down the tree
    if (value < root->value) {
        root->left = insert(root->left, value);
```
