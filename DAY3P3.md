# Spiral Matrix II
---
- ## Question:
> Given a positive integer n, generate an n x n matrix filled with elements from 1 to n2 in spiral order.
> 
![ALT](https://assets.leetcode.com/uploads/2020/11/13/spiraln.jpg)
---
- ## Example:
> Input: n = 3
> 
> Output: [[1,2,3],[8,9,4],[7,6,5]]
---
- ## Solution:
**Code :**
```java
class Solution {
public int[][] generateMatrix(int n) {

    int top = 0;
    int bottom = n - 1;
    int left = 0;
    int right = n - 1;
    
    int counter = 1;
    
    int[][] matrix = new int[n][n];
    
    while(counter <= n * n){
        
        for(int i = left ; i <= right; i++){
            matrix[top][i] = counter++;
        }
        top++;
        
        for(int i = top; i <= bottom; i++){
            matrix[i][right] = counter++;
        }
        right--;
        
        for(int i = right; i>= left; i--){
            matrix[bottom][i] = counter++;
        }
        bottom--;
        
        for(int i = bottom; i >= top; i--){
            matrix[i][left] = counter++;
        }
        left++;
    }
    return matrix;
}
}
