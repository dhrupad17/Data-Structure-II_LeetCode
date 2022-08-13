# Find the Town Judge
---
- ## Question:
> In a town, there are n people labeled from 1 to n. There is a rumor that one of these people is secretly the town judge.
> 
> If the town judge exists, then:
> 
>- The town judge trusts nobody.
>- Everybody (except for the town judge) trusts the town judge.
>- There is exactly one person that satisfies properties 1 and 2.
>- You are given an array trust where trust[i] = [ai, bi] representing that the person labeled ai trusts the person labeled bi.
>
> Return the label of the town judge if the town judge exists and can be identified, or return -1 otherwise.
---
- ## Example:
> Input: n = 2, trust = [[1,2]]
> 
> Output: 2
---
- ## Solution:
**Code :**
```java
class Solution {
    public int findJudge(int n, int[][] trust) {
        int[] help=new int[n+1];
        for(int[] p: trust)
        {
            help[p[0]]--;
            help[p[1]]++;
        }
        for(int i=1;i<help.length;i++)
        {
         if(help[i]==n-1)
             return i;
        }
        return -1;
    }
}
