# Kth Largest Element in an Array
---
- ## Question:
> Given an integer array nums and an integer k, return the kth largest element in the array.
> 
> Note that it is the kth largest element in the sorted order, not the kth distinct element.
> 
> You must solve it in O(n) time complexity.
---
- ## Example:
> Input: nums = [3,2,1,5,6,4], k = 2
> 
> Output: 5
---
- ## Solution:
**Code :**
```java
class Solution {
    public int findKthLargest(int[] nums, int k) {
        int n=nums.length;
        Arrays.sort(nums);
        return nums[n-k];
    }
}
