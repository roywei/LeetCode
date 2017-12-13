### 285. Inorder Successor in BST

[Link](https://leetcode.com/problems/inorder-successor-in-bst/description/):

> Description
>
> Given a binary search tree and a node in it, find the in-order successor of that node in the BST.
>
> **Note**: If the given node has no in-order successor in the tree, return`null`.

## Solution

#### 子问题拆解

有右孩子，等于在右孩子里找最小node

如果没有右孩子，等于顺着parent网上找，第一个是左孩子的parent就是答案，所以需要一个parent pointer

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode inorderSuccessor(TreeNode root, TreeNode p) {
        if(root == null || p == null)
            return null;
        if(p.right != null){
            return findMin(p.right);
        }
        if(root == p)
            return null;
        HashMap<TreeNode, TreeNode> parent = new HashMap<>();
        findP(root, p, parent);
        parent.put(root, null);
        TreeNode successor = parent.get(p);
        while(p != root && successor.left != p){
            p = successor;
            successor = parent.get(successor);
        }
        return successor;

    }
    
    public void findP(TreeNode root, TreeNode p, HashMap<TreeNode, TreeNode> parent){
        if(root == p)
            return;
        if(root.left != null){
            parent.put(root.left, root);
            findP(root.left, p, parent);
        }
        if(root.right != null){
            parent.put(root.right, root);
            findP(root.right, p, parent);
        }
    }
    
    public TreeNode findMin(TreeNode root){
        if(root == null)
            return null;
        if(root.left == null)
            return root;
        else
            return findMin(root.left);
    }
}
```

## Analysis

## Reference

http://www.jiuzhang.com/solution/inorder-successor-in-binary-search-tree/

http://www.jiuzhang.com/solution/inorder-successor-in-bst/



