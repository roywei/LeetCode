# Third Max Number

Link:[414](#)

> Description
>
> Given a**non-empty**array of integers, return the**third**maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O\(n\).
>
> **Example 1:**
>
> ```
> Input:
>  [3, 2, 1]
>
>
> Output:
>  1
>
>
> Explanation:
>  The third maximum is 1.
> ```
>
> **Example 2:**
>
> ```
> Input:
>  [1, 2]
>
>
> Output:
>  2
>
>
> Explanation:
>  The third maximum does not exist, so the maximum (2) is returned instead.
> ```
>
> **Example 3:**
>
> ```
> Input:
>  [2, 2, 3, 1]
>
>
> Output:
>  1
>
>
> Explanation:
>  Note that the third maximum here means the third maximum distinct number.
> Both numbers with value 2 are both considered as second maximum.
> ```

## Solution

#### 子问题拆解

#### 过程可视化

#### 打破假设

数组里有Integer.MIN\_VALUE怎么办，用null initialize，注意改变Integer class方便比较，最开始的continue case

#### 类比

## Code

```java
//Java
class Solution {
    public int thirdMax(int[] nums) {
        if(nums == null || nums.length < 1)
            return -1;
        Integer first, second, third;
        first = second = third = null;
        for(Integer n : nums){
            if(n.equals(first) || n.equals(second) || n.equals(third))
                continue;
            if(first == null || n > first){
                third = second;
                second = first;
                first = n;
            }else if( second == null || n > second ){
                third = second;
                second = n;
            }else if( third == null || n > third ){
                third = n;
            }
        }
        if(third == null)
            return first;
        else
            return third;

    }
}
```

## Analysis

## Reference



