# Reverse Nodes in k-Group
---
- ## Question:
> Given the head of a linked list, reverse the nodes of the list k at a time, and return the modified list.
> 
> k is a positive integer and is less than or equal to the length of the linked list. If the number of nodes is not a multiple of k then left-out nodes, in the end, should remain as it is.
> 
> You may not alter the values in the list's nodes, only nodes themselves may be changed.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/10/03/reverse_ex1.jpg)
> Input: head = [1,2,3,4,5], k = 2
> 
> Output: [2,1,4,3,5]
---
- ## Solution:
**Code :**
```java
class Solution {
    public ListNode reverseKGroup(ListNode head, int k) {
        ListNode curr=head;
        int count=0;
        while(curr!=null && count!=k)
        {
            curr=curr.next;
            count++;
        }
        if(count==k)
        {
            curr=reverseKGroup(curr,k);
            while(count-- >0)
            {
                ListNode temp=head.next;
                head.next=curr;
                curr=head;
                head=temp;
            }
            head=curr;
        }
        return head;
    }
}
