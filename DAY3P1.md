# Pascal's Triangle II
---
- ## Question:
> Given an integer rowIndex, return the rowIndexth (0-indexed) row of the Pascal's triangle.
> 
> In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:
> 
![ALT](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)
---
- ## Example:
> Input: rowIndex = 3
> 
> Output: [1,3,3,1]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> getRow(int rowIndex) {
        List<Integer> list=new ArrayList<>();
        for(int i=0;i<rowIndex+1;i++)
        {
            list.add(1);
            for(int j=i-1;j>0;j--)
            {
                list.set(j,list.get(j-1)+list.get(j));
            }
        }
        return list;
    }
}
