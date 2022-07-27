# Single Number
---
- ## Question:
> Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.
> 
> You must implement a solution with a linear runtime complexity and use only constant extra space.
---
- ## Example:
> Input: nums = [2,2,1]
> 
> Output: 1
---
- ## Solution:
**Code :**
```java
class Solution {
    public int singleNumber(int[] nums) {
       int result=0;
        for(int i: nums)
        {
            result=result^i;
        }
        return result;
    }
}
