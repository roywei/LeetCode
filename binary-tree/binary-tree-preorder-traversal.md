# 144. Binary Tree Preorder Traversal

Link: [144](https://leetcode.com/problems/binary-tree-preorder-traversal/description/)

> Description
>
> Given a binary tree, return thepreordertraversal of its nodes' values.
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
> return`[1,2,3]`.
>
> **Note:**Recursive solution is trivial, could you do it iteratively?

## Solution 1\(非递归\)

#### 子问题拆解

visit root之后，如果有左孩子，先visit左孩子，直到为空，才去最近一层的右孩子，这种特性，联想到stack LIFO

1. push root
2. while stack is not empty, pop, add to result
3. push right child\(**把优先访问的放在后面push近stack**\)
4. push left child

## Solution 2\(递归\)

#### 子问题拆解

每一次traverse都是按照同样的思路，先往左走，左边走到头再往又走，联想到递归

1. add root to result
2. traverse left
3. traverse right

## Solution 3\(分治\)

#### 子问题拆解

拆分成小问题，在每一层的输出都是，先输出root，然后输出所有左边的结果，最后输出所有右边的结果

## Code

```java
//Java
/**
  * 本代码由九章算法编辑提供。版权所有，转发请注明出处。
  * - 九章算法致力于帮助更多中国人找到好的工作，教师团队均来自硅谷和国内的一线大公司在职工程师。
  * - 现有的面试培训课程包括：九章算法班，系统设计班，算法强化班，Java入门与基础算法班，Android 项目实战班，Big Data 项目实战班，
  * - 更多详情请见官方网站：http://www.jiuzhang.com/?source=code
  */ 

Version 0: Non-Recursion (Recommend)
/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        List<Integer> preorder = new ArrayList<>();
        if(root == null)
            return preorder;
        Stack<TreeNode> stack = new Stack<>();
        TreeNode node = root;
        while(node != null || !stack.empty()){
            while(node != null){
                stack.push(node);
                preorder.add(node.val);
                node = node.left;
            }
            if(!stack.empty()){
                //这是node为空， 左边走不下去了，回到上一次的根，即stack最上面的
                node = stack.pop();
                node = node.right;
            }
        }
        return preorder;
    }
}

//Version 1: Traverse
public class Solution {
    public ArrayList<Integer> preorderTraversal(TreeNode root) {
        ArrayList<Integer> result = new ArrayList<Integer>();
        traverse(root, result);
        return result;
    }
    // 把root为跟的preorder加入result里面
    private void traverse(TreeNode root, ArrayList<Integer> result) {
        if (root == null) {
            return;
        }

        result.add(root.val);
        traverse(root.left, result);
        traverse(root.right, result);
    }
}

//Version 2: Divide & Conquer
public class Solution {
    public ArrayList<Integer> preorderTraversal(TreeNode root) {
        ArrayList<Integer> result = new ArrayList<Integer>();
        // null or leaf
        if (root == null) {
            return result;
        }

        // Divide
        ArrayList<Integer> left = preorderTraversal(root.left);
        ArrayList<Integer> right = preorderTraversal(root.right);

        // Conquer
        result.add(root.val);
        result.addAll(left);
        result.addAll(right);
        return result;
    }
}
```

## Analysis

O\(n\)

## Reference



