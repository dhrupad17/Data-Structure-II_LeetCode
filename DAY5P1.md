# Increasing Triplet Subsequence
---
- ## Question:
> Given an integer array nums, return true if there exists a triple of indices (i, j, k) such that i < j < k and nums[i] < nums[j] < nums[k]. If no such indices exists, return false.
---
- ## Example:
> Input: nums = [1,2,3,4,5]
> 
> Output: true
> 
> Explanation: Any triplet where i < j < k is valid.
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean increasingTriplet(int[] nums) {
        int min=Integer.MAX_VALUE;
        int min2=Integer.MAX_VALUE;
        for(int num: nums)
        {
            if(num<=min)
                min=num;
            else if(num<min2)
                min2=num;
            else if(num>min2)
                return true;
        }
        return false;
    }
}
