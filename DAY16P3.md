# Delete Node in a BST
---
- ## Question:
> Given a root node reference of a BST and a key, delete the node with the given key in the BST. Return the root node reference (possibly updated) of the BST.
> 
> Basically, the deletion can be divided into two stages:
> 
>- Search for a node to remove.
>- If the node is found, delete the node.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/09/04/del_node_1.jpg)
> Input: root = [5,3,6,2,4,null,7], key = 3
> 
> Output: [5,4,6,2,null,null,7]
---
- ## Solution:
**Code :**
```java
class Solution {
    public TreeNode deleteNode(TreeNode root, int key) {
        if(root==null)
            return null;
        if(key<root.val)
        {
            root.left=deleteNode(root.left,key);
            return root;
        }
        else if(key>root.val)
        {
            root.right=deleteNode(root.right,key);
            return root;
        }
        else
        {
            if(root.left==null)
                return root.right;
            else if(root.right==null)
                return root.left;
            else
            {
                TreeNode min=root.right;
                while(min.left!=null)
                {
                    min=min.left;
                }
                root.val=min.val;
                root.right=deleteNode(root.right,min.val);
                return root;
            }
        }
    }
}
