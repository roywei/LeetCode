# 33. Search in Rotated Sorted Array

Link:[33](https://leetcode.com/problems/search-in-rotated-sorted-array/description/)

> Description:
>
> Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.
>
> \(i.e.,`0 1 2 4 5 6 7`might become`4 5 6 7 0 1 2`\).
>
> You are given a target value to search. If found in the array return its index, otherwise return -1.
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
    public int search(int[] nums, int target) {
        if(nums.length == 0)
            return -1;
        int minIndex = findMinIndex(nums);
        if(minIndex == 0)
            return binarySearch(nums, target);

        if(nums[0] > target){
            int result = binarySearch(Arrays.copyOfRange(nums,minIndex,nums.length), target);
            if(result == -1)
                return result;
            else
                return minIndex + result;
        }

        else if (nums[0] < target)
            return binarySearch(Arrays.copyOfRange(nums,0,minIndex), target);
        else
            return 0;
    }

    public int binarySearch(int[] nums, int target){
        if(nums.length == 0)
            return -1;
        int start = 0;
        int end = nums.length - 1;
        while(start + 1 < end){
            int mid = start + (end - start)/2;
            if(nums[mid] == target)
                return mid;
            else if(nums[mid] > target)
                end = mid;
            else
                start = mid;
        }
        if(nums[start] == target)
            return start;
        if(nums[end] == target)
            return end;
        return -1;
    }

    public int findMinIndex(int[] nums) {
        if(nums.length == 0)
            return -1;

        int start = 0;
        int end = nums.length - 1;
        while(start + 1 < end){
            int mid = start + (end - start)/2;
            if(nums[mid] > nums[mid+1])
                return mid+1;
            else if(nums[mid] < nums[mid+1] && nums[mid] < nums[mid-1])
                return mid;
            else if(nums[mid] < nums[mid+1] && nums[mid] > nums[start])
                start = mid;
            else if(nums[mid] < nums[mid+1] && nums[mid] < nums[start])
                end = mid;
        }
        if(nums[start] > nums[end])
            return end;
        //return nums[0] not nums[start], test case[1,2,3]
        return 0;
    }

}
```

## Analysis

注意：

1. 先找到最小值的index，解法见[153](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/description/)
2. copy array 开始index是包括，结束index不包括

## Reference



