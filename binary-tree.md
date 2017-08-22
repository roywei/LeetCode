# Binary Tree

## Introduction

[Binary Tree](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Trees/trees.html)

## Traversals

A traversal is a process that visits all the nodes in the tree. Since a tree is a nonlinear data structure, there is no unique traversal. We will consider several traversal algorithms with we group in the following two kinds

* **depth-first traversal**
* **breadth-first traversal**

There are three different types of depth-first traversals, :

* **PreOrder** traversal - visit the parent first and then left and right children;
* **InOrder** traversal - visit the left child, then the parent and the right child;
* **PostOrder** traversal - visit left child, then the right child and then the parent;

There is only one kind of breadth-first traversal--the level order traversal. This traversal visits nodes by levels **from top to bottom and from left to right.**

| As an example consider the following tree and its four traversals:  PreOrder - 8, 5, 9, 7, 1, 12, 2, 4, 11, 3 InOrder - 9, 5, 1, 7, 2, 12, 8, 4, 3, 11 PostOrder - 9, 1, 2, 12, 7, 5, 3, 11, 4, 8 LevelOrder - 8, 5, 4, 9, 7, 11, 1, 12, 3, 2 |
| :--- |


![](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Trees/pix/tree1.bmp)

An **Euler tour** is a walk around the binary tree where each edge is treated as a wall, which you cannot cross. In this walk each node will be visited either on the left, or under the below, or on the right. The Euler tour in which we visit nodes on the left produces a preorder traversal. When we visit nodes from the below, we get an inorder traversal. And when we visit nodes on the right, we get a postorder traversal.\(顺着箭头走，从root开始，碰到该颜色的墙壁才记录，都从E开始走，preorder第一个是E，inorder和postorder都是H\)

![](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Trees/pix/traversalEuler.bmp)

## 

## Example:

```java

```



