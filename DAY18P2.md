# Serialize and Deserialize Binary Tree
---
- ## Question:
> Serialization is the process of converting a data structure or object into a sequence of bits so that it can be stored in a file or memory buffer, or transmitted across a network connection link to be reconstructed later in the same or another computer environment.
> 
> Design an algorithm to serialize and deserialize a binary tree. There is no restriction on how your serialization/deserialization algorithm should work. You just need to ensure that a binary tree can be serialized to a string and this string can be deserialized to the original tree structure.
> 
> Clarification: The input/output format is the same as how LeetCode serializes a binary tree. You do not necessarily need to follow this format, so please be creative and come up with different approaches yourself.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/09/15/serdeser.jpg)
> Input: root = [1,2,3,null,null,4,5]
> 
> Output: [1,2,3,null,null,4,5]
---
- ## Solution:
**Code :**
```java
public class Codec {

    public void serializeRecursive(TreeNode root, StringBuilder output) {
        if (root == null) {
         output.append("null,");
        return;
        }

        output.append(root.val).append(",");
        serializeRecursive(root.left, output);
        serializeRecursive(root.right, output);
    }
    public String serialize(TreeNode root) {
        StringBuilder output = new StringBuilder();
        serializeRecursive(root, output);
        output.deleteCharAt(output.length() - 1);
        return output.toString();
    }
    public TreeNode deserializeRecursive(List<String> input) {
        String currentVal = input.remove(0);
        if (currentVal.equals("null")) 
        {
            return null;
        }
        TreeNode root = new TreeNode(Integer.parseInt(currentVal));
        root.left = deserializeRecursive(input);
        root.right = deserializeRecursive(input);
        return root;
    }
    public TreeNode deserialize(String data) {
        List<String> input = new ArrayList<>(Arrays.asList(data.split(",")));
        return deserializeRecursive(input);
     }
}
