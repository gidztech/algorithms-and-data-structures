# Trees
A tree is a "nonlinear data structure that is used to store data in a hierarchical manner". (McMillan)

## Binary Tree
A binary tree has nodes which can have no more than 2 child nodes.

![Binary tree](https://i.imgur.com/tLSgEge.png)

## Binary Search Tree (BST)
A binary search tree stores the smaller values in the nodes on the left and the larger in the nodes on the right.

![Binary search tree](https://i.imgur.com/Bn6hHNI.png)

If the tree is unbalanced, then the performance can degrade to the same as a LinkedList, `O(n)`. The implementation should keep the tree
balanced, which will typically produce `O(log n)` for search, insert and delete operations.

Instead of writing out a full implementation of a BST in JavaScript, see this existing snippet:
https://mgechev.github.io/javascript-algorithms/data-structures_binary-search-tree.js.html

### Uses
BST's are efficient for dynamically changing data sets that are sortable. Linear structures like arrays are good for searching with binary
search, but are slower for insertion and removals. Rather than storing the data contiguously in order, the data is maintained in separate
nodes, which are linked to existing nodes.
