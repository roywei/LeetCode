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

另一种直观的解题思路，直觉的解法是，先放入空集，然后放入所有1开头的集合，再放入2开头的集合，再放入3开头的集合。

放入1开头的集合过程，nums = \[1,2,3\]：

1. temp array = \[\]为起点, 可以放入result
2. temp放入1: \[1\], 可以放入result
3. temp放入2: \[1,2\] , 可以放入result
4. temp放入3: \[1,2,3\], 可以放入result
5. 没有可以放入的数字，backtrack 回\[1,2\], 依然没有可以放入的数字，再backtrack回\[1\], 再回\[\]
6. temp放入\[2\], 可以放入result
7. 以此类推放入\[2,3\], backtrack 2次，放入\[3\]



#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Solution 1:
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

```java
// Solution 2
public List<List<Integer>> subsets(int[] nums) {
    List<List<Integer>> list = new ArrayList<>();
    Arrays.sort(nums);
    backtrack(list, new ArrayList<>(), nums, 0);
    return list;
}

private void backtrack(List<List<Integer>> list , List<Integer> tempList, int [] nums, int start){
    list.add(new ArrayList<>(tempList));
    for(int i = start; i < nums.length; i++){
        tempList.add(nums[i]);
        backtrack(list, tempList, nums, i + 1);
        tempList.remove(tempList.size() - 1);
    }
}
```

## Analysis

## Reference

1. 模板： [https://discuss.leetcode.com/topic/46159/a-general-approach-to-backtracking-questions-in-java-subsets-permutations-combination-sum-palindrome-partitioning](https://discuss.leetcode.com/topic/46159/a-general-approach-to-backtracking-questions-in-java-subsets-permutations-combination-sum-palindrome-partitioning)
2. 其他解法：[https://soulmachine.gitbooks.io/algorithm-essentials/content/java/brute-force/subsets.html](https://soulmachine.gitbooks.io/algorithm-essentials/content/java/brute-force/subsets.html)



