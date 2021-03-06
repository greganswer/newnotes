# Tree

- [Summary](#summary)
- [Details](#details)
  - [Binary tree](#binary-tree)
  - [A Binary Search Tree](#a-binary-search-tree)
  - [AVL Trees](#avl-trees)
  - [Red Black Trees](#red-black-trees)
  - [Trie](#trie)
- [Examples](#examples)
- [References](#references)

## Summary

**Components of a tree**
![Tree description](/images/tree_description.png)
source: https://dev.to/fahimulhaq/top-8-data-structures-for-coding-interviews-and-practice-interview-questions-2pb

**Types of trees**
![Full, complete and perfect binary trees](/images/full_complete_and_perfect_binary_trees.png)
source: https://study.com/academy/lesson/binary-trees-applications-implementation.html

- A tree is a type of graph

## Details

### Binary tree

- Each node can have 0-2 child nodes
- Each child can only have 1 parent
- Their size is flexible

**Perfect Binary tree**
- Each child node has 0 or 2 nodes (not 1)
- The bottom layer of the tree has all nodes
- Each level has double the number of nodes in the previous level
- Half of all nodes are on the bottom level
- The sum of the nodes on the last level is equal to the sum of the nodes on all the other levels + 1

**Unbalanced Binary search trees**
- have a O(n) linear time complexity for all operations because they basically become a Linked List that requires `n` traversal

**Full Binary tree**
- Each child node has 0 or 2 nodes (not 1)

### A Binary Search Tree

A Binary Search Tree (BST) is a binary tree in which each vertex has only up to 2 children that satisfies BST property: All vertices in the left subtree of a vertex must hold a value smaller than its own and all vertices in the right subtree of a vertex must hold a value larger than its own

### AVL Trees

[Animation](https://www.cs.usfca.edu/~galles/visualization/AVLtree.html)
[How it Works](https://medium.com/basecs/the-little-avl-tree-that-could-86a3cae410c7)

### Red Black Trees

[Animation](https://www.cs.usfca.edu/~galles/visualization/RedBlack.html)
[How it Works](https://medium.com/basecs/painting-nodes-black-with-red-black-trees-60eacb2be9a5)

### Trie

- A trie has a O(n) time complexity, where n is the length of the word being searched.

## Examples

## References

- https://stackoverflow.com/questions/13852870/red-black-tree-over-avl-tree