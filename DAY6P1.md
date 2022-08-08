# Add Strings
---
- ## Question:
> Given two non-negative integers, num1 and num2 represented as string, return the sum of num1 and num2 as a string.
> 
> You must solve the problem without using any built-in library for handling large integers (such as BigInteger). You must also not convert the inputs to integers directly.
---
- ## Example:
> Input: num1 = "11", num2 = "123"
> 
> Output: "134"
---
- ## Solution:
**Code :**
```java
class Solution {
    public String addStrings(String num1, String num2) {
        
        int num1Len = num1.length() - 1;
        int num2Len = num2.length() - 1;
        int maxLen = Math.max(num1Len, num2Len) + 2;
        char[] res = new char[maxLen];
        int sum = 0;
        
        while(num1Len >= 0 || num2Len >= 0) {
            
            if(num1Len >= 0) {
                sum += num1.charAt(num1Len--) - '0';
            }
            
            if(num2Len >= 0) {
                sum += num2.charAt(num2Len--) - '0';
            }
            
            res[--maxLen] = (char)((sum % 10) + '0');
            sum /= 10;
        }
        
        if(sum != 0) {
            res[0] = '1';
            return String.valueOf(res);
        }
        
        return String.valueOf(res, 1, res.length - 1);
    }
}
