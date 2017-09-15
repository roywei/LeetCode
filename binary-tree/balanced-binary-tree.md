# 110. Balanced Binary Tree

  
[Link](https://leetcode.com/problems/balanced-binary-tree/description/):

> Description
>
> Given a binary tree, determine if it is height-balanced.
>
> For this problem, a height-balanced binary tree is defined as a binary tree in which the depth of the two subtrees ofeverynode never differ by more than 1.

## Solution

#### 子问题拆解

这题拆解成两个子问题，对于每一个node, 检查：

1. left, right是否balance
2. left, right深度是否相差1以上

直观的用bottom up的recursion解法，但是两个检查标准都需要recursion，这样默认解法是O\(n^2\)

#### 过程可视化

#### 打破假设

能否在一个recursion里做到返回两种结果，有以下方法:

1. 返回resultType object, 有isBalanced 和 maxDepth两个field
2. 如果balanced就反回maxDepth，不balance直接返回-1，因为节点以下的深度不需要了
3. 用python :\)

#### 类比

## Code

```java
//Java
class Solution {
    public boolean isBalanced(TreeNode root){
        if(root == null)
            return true;
        int result = examTree(root);
        return result == -1 ? false : true;
    }
    public int examTree(TreeNode root){
        if(root == null)
            return 0;
        int left = examTree(root.left);
        int right = examTree(root.right);
        if(left == -1 || right == -1)
            return -1;
        else if(Math.abs(left-right) > 1)
            return -1;
        else
            return Math.max(left, right) + 1;
    }
    
    
    //** O(n^2) solution
    public boolean isBalanced(TreeNode root) {
        if(root == null)
            return true;
        boolean leftBalanced = isBalanced(root.left);
        boolean rightBalanced = isBalanced(root.right);
        if(leftBalanced && rightBalanced){
            int left = getDepth(root.left);
            int right = getDepth(root.right);
            if(Math.abs(left - right) > 1)
                return false;
            else
                return true;
        }else
            return false;
    }
    public int getDepth(TreeNode root){
        if(root == null)
            return 0;
        int left = getDepth(root.left);
        int right = getDepth(root.right);
        return Math.max(left, right) + 1;
    }
    */
}
```

## Analysis

## Reference



