# Swap Nodes in Pairs
---
- ## Question:
> Given a linked list, swap every two adjacent nodes and return its head. You must solve the problem without modifying the values in the list's nodes (i.e., only nodes themselves may be changed.)
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/10/03/swap_ex1.jpg)
> Input: head = [1,2,3,4]
> 
> Output: [2,1,4,3]
---
- ## Solution:
**Code :**
```java
class Solution {
    public ListNode swapPairs(ListNode head) {
        if(head==null || head.next==null)
            return head;
        ListNode second=head.next;
        ListNode third=second .next;
        second.next=head;
        head.next=swapPairs(third);
        return second;
    }
}
