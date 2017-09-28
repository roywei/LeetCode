## 93. Restore IP Addresses

From Hitachi

Link: [93](https://leetcode.com/problems/restore-ip-addresses/description/)

> Description
>
> Given a string containing only digits, restore it by returning all possible valid IP address combinations.
>
> For example:  
> Given`"25525511135"`,
>
> return`["255.255.11.135", "255.255.111.35"]`. \(Order does not matter\)

## Solution

#### 子问题拆解

本质是三个点的放置，组合问题肯定dfs，但是这里用for loop比递归容易写，for loop里做剪枝，注意验证IP需要network相关知识

#### 过程可视化

#### 打破假设

#### 类比

## Code

```java
//Java

class Solution {
    public List<String> restoreIpAddresses(String s) {
        List<String> result = new ArrayList<>();
        for(int i = 1; i<4 && i < s.length()-2; i++){
            for(int j = i+1; j<i+4 && j<s.length()-1; j++){
                for(int k = j+1; k<j+4 && k<s.length(); k++){
                    if( isValid(s.substring(0,i)) && 
                                isValid(s.substring(i,j)) && 
                                        isValid(s.substring(j,k)) && 
                                                isValid(s.substring(k,s.length()))){
                                                    String newip = s.substring(0,i) + "." + 
                                                              s.substring(i,j) + "." +
                                                              s.substring(j,k) + "."+
                                                              s.substring(k,s.length());
                                                    result.add(newip);
                                                }
                }
            }
        }
        return result;

    }

    public boolean isValid(String ip){
        if(ip.length() < 1 || ip.length() > 3){
            return false;
        }
        if(ip.length() > 1 && ip.charAt(0) == '0'){
            return false;
        }
        if(Integer.valueOf(ip) > 255){
            return false;
        }
        return true;
    }
}
```

## Analysis

## Reference



