# Product of Array Except Self
---
- ## Question:
> Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i].
> 
> The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.
> 
> You must write an algorithm that runs in O(n) time and without using the division operation.
---
- ## Example:
> Input: nums = [1,2,3,4]
> 
> Output: [24,12,8,6]
---
- ## Solution:
**Code :**
```java
class Solution{
public int[] productExceptSelf(int[] nums) {

    int len = nums.length;
    int [] output = new int[len];
    
    int leftMult = 1, rightMult = 1;
    
    for(int i = len-1; i >= 0; i--){
        output[i] = rightMult;
        rightMult *= nums[i];
    }
    for(int j = 0; j < len; j++){
        output[j] *= leftMult;
        leftMult *= nums[j];
       
    }
    
    return output; 

}
}
