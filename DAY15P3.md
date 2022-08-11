# Binary Tree Zigzag Level Order Traversal
---
- ## Question:
> Given the root of a binary tree, return the zigzag level order traversal of its nodes' values. (i.e., from left to right, then right to left for the next level and alternate between).
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/02/19/tree1.jpg)
> Input: root = [3,9,20,null,null,15,7]
> 
> Output: [[3],[20,9],[15,7]]
---
- ## Solution:
**Code :**
```java
class Solution {
    List<List<Integer>> list=new ArrayList<>();
    public List<List<Integer>> zigzagLevelOrder(TreeNode root) {
        zighelp(root,0,list);
        return list;
    }
    void zighelp(TreeNode Node,int level,List<List<Integer>> li)
    {
        if(Node!=null)
        {
            if(li.size()<=level)
                li.add(new ArrayList<>());
            if(level%2==0)
                li.get(level).add(Node.val);
            else
                li.get(level).add(0,Node.val);
            zighelp(Node.left,level+1,li);
            zighelp(Node.right,level+1,li);
        }
    }
}
