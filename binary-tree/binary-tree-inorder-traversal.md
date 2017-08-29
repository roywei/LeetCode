# 94. Binary Tree Inorder Traversal

Link: [94](https://leetcode.com/problems/binary-tree-inorder-traversal/description/)

> Description
>
> Given a binary tree, return theinordertraversal of its nodes' values.
>
> For example:  
> Given binary tree`[1,null,2,3]`,
>
> ```
>    1
>     \
>      2
>     /
>    3
> ```
>
> return`[1,3,2]`.
>
> **Note:**Recursive solution is trivial, could you do it iteratively?

## Solution

#### 子问题拆解

三种方法同理preorder，只是先输出左子树，然后根，最后右子树

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Java
 /**
  * 本代码由九章算法编辑提供。版权所有，转发请注明出处。
  * - 九章算法致力于帮助更多中国人找到好的工作，教师团队均来自硅谷和国内的一线大公司在职工程师。
  * - 现有的面试培训课程包括：九章算法班，系统设计班，算法强化班，Java入门与基础算法班，Android 项目实战班，Big Data 项目实战班，
  * - 更多详情请见官方网站：http://www.jiuzhang.com/?source=code
  */ 

/**
 * Definition of TreeNode:
 * public class TreeNode {
 *     public int val;
 *     public TreeNode left, right;
 *     public TreeNode(int val) {
 *         this.val = val;
 *         this.left = this.right = null;
 *     }
 * }
 */
public class Solution {
    /**
     * @param root: The root of binary tree.
     * @return: Inorder in ArrayList which contains node values.
     */
    public ArrayList<Integer> inorderTraversal(TreeNode root) {
        Stack<TreeNode> stack = new Stack<TreeNode>();
        ArrayList<Integer> result = new ArrayList<Integer>();
        TreeNode curt = root;
        while (curt != null || !stack.empty()) {
            while (curt != null) {
                stack.add(curt);
                curt = curt.left;
            }
            curt = stack.pop();
            result.add(curt.val);
            curt = curt.right;
        }
        return result;
    }
}


 /** Solution 2: recursive
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> inorder = new ArrayList<>();
        traverse(root, inorder);
        return inorder;
    }
    
    public void traverse(TreeNode node, List<Integer> inorder){
        if(node == null)
            return;
        traverse(node.left, inorder);
        inorder.add(node.val);
        traverse(node.right, inorder);
    }
*/

/** Solution 3: Divide and Conquer
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> inorder = new ArrayList<>();
        if(root == null)
            return inorder;
        List<Integer> left = inorderTraversal(root.left);
        List<Integer> right = inorderTraversal(root.right);
        
        inorder.addAll(left);
        inorder.add(root.val);
        inorder.addAll(right);
        return inorder;
    
    }
    **/
```

## Analysis

## Reference



