# Subsets

Link:[ 78](https://leetcode.com/problems/subsets/#/description)

> Given a set of **distinct **integers,nums, return all possible subsets.
>
> **Note:**The solution set must not contain duplicate subsets.
>
> For example,  
> If **nums**=`[1,2,3]`, a solution is:
>
> ```
> [
>   [3],
>   [1],
>   [2],
>   [1,2,3],
>   [1,3],
>   [2,3],
>   [1,2],
>   []
> ]
> ```

## Solution

#### 子问题拆解

##### 解法一：归纳法

手写一步步解题推导：

```
[] -> [ [] ]
[1] -> [ [], [1]]
[1,2] -> [ [], [1], [2], [1,2]]
```

归纳法得出:

1. base case: \[\] -&gt; \[ \[\] \]
2. 其他情况：输入nums的结果等于nums\[:-1\] 的结果，  加上nums\[:-1\] 的结果里的每一项array都加nums\[-1\], **存到输出结果里需要copy arraylist**
3. 处理corner case，nums = null, nums.length == 0

##### 解法二：Backtracking



#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Java
public class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> ret = new ArrayList<List<Integer>>();
        if(nums == null)
            return null;
        if(nums.length == 0){
            ret.add(new ArrayList<Integer>());
            return ret;
        }    

        int num = nums[nums.length - 1];
        List<List<Integer>> recurisveResult = subsets(Arrays.copyOf(nums, nums.length-1));
        for(List<Integer> item : recurisveResult){
            ret.add(new ArrayList<Integer>(item));
            item.add(num);
            ret.add(new ArrayList<Integer>(item));
        }

        return ret;
    }
}
```

## Analysis

## Reference



