# Word Pattern
---
- ## Question:
> Given a pattern and a string s, find if s follows the same pattern.
> 
> Here follow means a full match, such that there is a bijection between a letter in pattern and a non-empty word in s.
---
- ## Example:
> Input: pattern = "abba", s = "dog cat cat dog"
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean wordPattern(String pattern, String s) {
        String [] words=s.split(" ");
        if(words.length!=pattern.length())
            return false;
        Map key=new HashMap();
        for(Integer i=0;i<words.length;i++)
        {
            if(key.put(pattern.charAt(i),i)!=key.put(words[i],i))
                return false;
        }
        return true;
    }
}
