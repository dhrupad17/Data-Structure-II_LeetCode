# Minimum Number of Vertices to Reach All Nodes
---
- ## Question:
> Given a directed acyclic graph, with n vertices numbered from 0 to n-1, and an array edges where edges[i] = [fromi, toi] represents a directed edge from node fromi to node toi.
> 
> Find the smallest set of vertices from which all nodes in the graph are reachable. It's guaranteed that a unique solution exists.
> 
> Notice that you can return the vertices in any order.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2020/07/07/untitled22.png)
> Input: n = 6, edges = [[0,1],[0,2],[2,5],[3,4],[4,2]]
> 
> Output: [0,3]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<Integer> findSmallestSetOfVertices(int n, List<List<Integer>> edges) {
        List<Integer>ans=new ArrayList<Integer>();
        boolean indegree[]=new boolean[n];
        for(List<Integer>edge: edges)
        {
            indegree[edge.get(1)]=true;
        }
        for(int i=0;i<n;i++)
        {
            if(!indegree[i])
                ans.add(i);
        }
        return ans;
    }
}
