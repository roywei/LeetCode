# 145. Binary Tree Postorder Traversal

Link:[145](https://leetcode.com/problems/binary-tree-postorder-traversal/description/)

> Description
>
> Given a binary tree, return thepostordertraversal of its nodes' values.
>
> For example:  
> Given binary tree`{1,#,2,3}`,
>
> ```
>    1
>     \
>      2
>     /
>    3
> ```
>
> return`[3,2,1]`.
>
> **Note:**Recursive solution is trivial, could you do it iteratively?

## Solution

#### 子问题拆解

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
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
    // Solution: Non Recursive
    public List<Integer> postorderTraversal(TreeNode root) {
        
        List<Integer> postorder = new ArrayList<>();
        if(root == null)
            return postorder;
        Stack<TreeNode> stack = new Stack<>();
        TreeNode node = root;
        TreeNode lastVisit = root;
        while(node != null || !stack.empty()){
            while(node != null){
                stack.push(node);
                node = node.left;
            }
            node = stack.peek();
            if(node.right == null || node.right == lastVisit){
                postorder.add(node.val);
                node = stack.pop();
                lastVisit = node;
                node = null;
            }else{
                node = node.right;
            }
        }
        return postorder;
    }
    /** Soulution 2 recursion
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> postorder = new ArrayList<>();
        traverse(root, postorder);
        return postorder;

    }
    
    public void traverse(TreeNode node, List<Integer> postorder){
        if(node == null)
            return;
        traverse(node.left, postorder);
        traverse(node.right, postorder);
        postorder.add(node.val);
    }
    */ 
    /** Solution 1 Divide and Conquer
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> postorder = new ArrayList<>();
        if(root == null)
            return postorder;
        List<Integer> left = postorderTraversal(root.left);
        List<Integer> right = postorderTraversal(root.right);
        postorder.addAll(left);
        postorder.addAll(right);
        postorder.add(root.val);
        return postorder;

    }
    */
}/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    // Solution: Non Recursive
    public List<Integer> postorderTraversal(TreeNode root) {
        
        List<Integer> postorder = new ArrayList<>();
        if(root == null)
            return postorder;
        Stack<TreeNode> stack = new Stack<>();
        TreeNode node = root;
        TreeNode lastVisit = root;
        while(node != null || !stack.empty()){
            while(node != null){
                stack.push(node);
                node = node.left;
            }
            node = stack.peek();
            if(node.right == null || node.right == lastVisit){
                postorder.add(node.val);
                node = stack.pop();
                lastVisit = node;
                node = null;
            }else{
                node = node.right;
            }
        }
        return postorder;
    }
    /** Soulution 2 recursion
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> postorder = new ArrayList<>();
        traverse(root, postorder);
        return postorder;

    }
    
    public void traverse(TreeNode node, List<Integer> postorder){
        if(node == null)
            return;
        traverse(node.left, postorder);
        traverse(node.right, postorder);
        postorder.add(node.val);
    }
    */ 
    /** Solution 1 Divide and Conquer
    public List<Integer> postorderTraversal(TreeNode root) {
        List<Integer> postorder = new ArrayList<>();
        if(root == null)
            return postorder;
        List<Integer> left = postorderTraversal(root.left);
        List<Integer> right = postorderTraversal(root.right);
        postorder.addAll(left);
        postorder.addAll(right);
        postorder.add(root.val);
        return postorder;

    }
    */
}
```

## Analysis

## Reference



