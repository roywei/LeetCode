# Solution Template

Link: [28](https://leetcode.com/problems/implement-strstr/#/description)

> Implement strStr\(\).
>
> Returns the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

## Solution

#### 子问题拆解

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
public class Solution {
    public int strStr(String haystack, String needle) {
        if (haystack == null || needle == null || needle.length() > haystack.length())
            return -1;

        for(int p1 = 0; p1 < (haystack.length() -  needle.length() + 1); p1 ++){
            for(int p2 = 0; ; p2 ++){
                //if exist needle
                if(p2 == needle.length())
                    return p1;
                //check equality
                if(haystack.charAt(p1+p2) != needle.charAt(p2))
                    break;
            }
        }
        return -1;
    }
}
```

## Analysis



## Reference

[strStr](#)

