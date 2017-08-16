# Solution Template

Link: [278](https://leetcode.com/problems/first-bad-version/#/description)

> Description:
>
> Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.
>
> \(i.e.,`0 1 2 4 5 6 7`might become`4 5 6 7 0 1 2`\).
>
> Find the minimum element.
>
> You may assume no duplicate exists in the array.

## Solution

#### 子问题拆解

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Java
public class Solution {
    public int findMin(int[] nums) {
        if(nums.length == 0)
            return -1;
        
        int start = 0;
        int end = nums.length - 1;
        while(start + 1 < end){
            int mid = start + (end - start)/2;
            if(nums[mid] > nums[mid+1])
                return nums[mid+1];
            else if(nums[mid] < nums[mid+1] && nums[mid] < nums[mid-1])
                return nums[mid];
            else if(nums[mid] < nums[mid+1] && nums[mid] > nums[start])
                start = mid;
            else if(nums[mid] < nums[mid+1] && nums[mid] < nums[start])
                end = mid;
        }
        if(nums[start] > nums[end])
            return nums[end];
        //return nums[0] not nums[start], test case[1,2,3]
        return nums[0];
    }
}
```

## Analysis

注意最后可能有顺序，没rotate的情况，这时应该返回nums\[0\]最小

## Reference



