# Partition Labels
---
- ## Question:
> You are given a string s. We want to partition the string into as many parts as possible so that each letter appears in at most one part.
> 
> Note that the partition is done so that after concatenating all the parts in order, the resultant string should be s.
> 
> Return a list of integers representing the size of these parts.
---
- ## Example:
> Input: s = "ababcbacadefegdehijhklij"
> 
> Output: [9,7,8]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> partitionLabels(String s) {
        Map<Character,Integer>map=new HashMap<>();
        for(int i=0;i<s.length();i++)
        {
            char ch=s.charAt(i);
            map.put(ch,i);
        }
        
        List<Integer> res=new ArrayList<>();
        int max=0;
        int prev=-1;
        
        for(int i=0;i<s.length();i++)
        {
            char ch=s.charAt(i);
            max=Math.max(max,map.get(ch));
            if(max==i)
            {
                res.add(max-prev);
                prev=max;
            }
        }
        return res;
    }
}
