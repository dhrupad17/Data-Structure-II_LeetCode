# Path Sum II
---
- ## Question:
> Given the root of a binary tree and an integer targetSum, return all root-to-leaf paths where the sum of the node values in the path equals targetSum. Each path should be returned as a list of the node values, not node references.\
> 
> A root-to-leaf path is a path starting from the root and ending at any leaf node. A leaf is a node with no children.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/01/18/pathsumii1.jpg)
> Input: root = [5,4,8,11,null,13,4,7,2,null,null,5,1], targetSum = 22
> 
> Output: [[5,4,11,2],[5,8,4,5]]
---
- ## Solution:
**Code :**
```java
class Solution {
        public List<List<Integer>> pathSum(TreeNode root, int target) {
        List<List<Integer>> ans=new ArrayList<>();
        fn( root, target,new ArrayList<>() , ans);
        
        return ans;
    }
    void fn( TreeNode root, int target, List<Integer> pres_ans, List<List<Integer>> ans){
        
        if( root== null) return;
        
        else if( root.left==null && root.right== null && target-root.val==0){
            pres_ans.add(root.val);
            ans. add( new ArrayList<>(pres_ans));
        }
        else {
            List<Integer> temp= new ArrayList<>(pres_ans);
            pres_ans.add(root.val);
            fn( root.left,target-root.val,pres_ans , ans);
            temp.add(root.val);
             fn( root.right,target-root.val, temp, ans);
        }
        
    }
}
