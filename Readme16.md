# Trees
A tree data structure is a non-linear data structure because it does not store in a sequential manner. It is a hierarchical structure as elements in a Tree are arranged in multiple levels.

In the Tree data structure, the topmost node is known as a root node. Each node contains some data, and data can be of any type.

### Common Terminology
Node - A Tree node is a component which may contain its own values, and references to other nodes.

Root - The root is the node at the beginning of the tree.

K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.

Left - A reference to one child node, in a binary tree.

Right - A reference to the other child node, in a binary tree.

Edge - The edge in a tree is the link between a parent and child node.

Leaf - A leaf is a node that does not have any children.

Height - The height of a tree is the number of edges from the root to the furthest leaf.


### Some basic terms used in Tree data structure.
![](https://static.javatpoint.com/ds/images/tree2.png)


Properties of Tree data structure:

Recursive data structure: The tree is also known as a recursive data structure. A tree can be defined as recursively because the distinguished node in a tree data structure is known as a root node. The root node of the tree contains a link to all the roots of its subtrees. The left subtree is shown in the yellow color in the below figure, and the right subtree is shown in the red color. The left subtree can be further split into subtrees shown in three different colors. Recursion means reducing something in a self-similar manner. So, this recursive property of the tree data structure is implemented in various applications.

![](https://static.javatpoint.com/ds/images/tree3.png)

Number of edges: If there are n nodes, then there would n-1 edges. Each arrow in the structure represents the link or path. Each node, except the root node, will have atleast one incoming link known as an edge. There would be one link for the parent-child relationship.

Depth of node x: The depth of node x can be defined as the length of the path from the root to the node x. One edge contributes one-unit length in the path. So, the depth of node x can also be defined as the number of edges between the root node and the node x. The root node has 0 depth.

Height of node x: The height of node x can be defined as the longest path from the node x to the leaf node.


### Implementation of Tree
The tree data structure can be created by creating the nodes dynamically with the help of the pointers. The tree in the memory can be represented as shown below:
![](https://static.javatpoint.com/ds/images/tree4.png)

he structure of a node can be defined as:

example
```
struct node  
{  
  int data;  
struct node *left;  
struct node *right;   
}  
```
### Types of Tree data structure
1- General tree: The general tree is one of the types of tree data structure. In the general tree, a node can have either 0 or maximum n number of nodes. There is no restriction imposed on the degree of the node (the number of nodes that a node can contain). The topmost node in a general tree is known as a root node. The children of the parent node are known as subtrees.
![](https://static.javatpoint.com/ds/images/types-of-tree1.png)


2- Binary tree: Here, binary name itself suggests two numbers, i.e., 0 and 1. In a binary tree, each node in a tree can have utmost two child nodes. Here, utmost means whether the node has 0 nodes, 1 node or 2 nodes.

![](https://static.javatpoint.com/ds/images/types-of-tree2.png)


# Referaces
[Trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/Trees.html) <br/>
[Tree Data Structure](https://www.javatpoint.com/tree#:~:text=A%20tree%20data%20structure%20is%20a%20non%2Dlinear%20data%20structure,can%20be%20of%20any%20type.) 