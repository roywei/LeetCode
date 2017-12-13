second uniquely largest number

```java
public int secondLargest(int[] nums){
    int i, first, second;
    if(nums == null || nums.length < 2)
        return -1;
    first = second = Integer.MIN_VALUE;
    for(i = 0; i < nums.length; i++){
        if(nums[i] > first){
            second = first;
            first = nums[i];
        }else if(nums[i] > second && nums[i] != first)
             second = nums[i];
     }
     if(second == Integer.MIN_VALUE)
         return -1;
     else
         return second;
}
```



