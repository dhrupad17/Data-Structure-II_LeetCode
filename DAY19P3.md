# Keys and Rooms
---
- ## Question:
> There are n rooms labeled from 0 to n - 1 and all the rooms are locked except for room 0. Your goal is to visit all the rooms. However, you cannot enter a locked room without having its key.
> 
> When you visit a room, you may find a set of distinct keys in it. Each key has a number on it, denoting which room it unlocks, and you can take all of them with you to unlock the other rooms.
> 
> Given an array rooms where rooms[i] is the set of keys that you can obtain if you visited room i, return true if you can visit all the rooms, or false otherwise.
---
- ## Example:
> Input: rooms = [[1],[2],[3],[]]
> 
> Output: true
---
- ## Solution:
**Code :**
```java
class Solution {
    public boolean canVisitAllRooms(List<List<Integer>> rooms) {
        boolean[] visited=new boolean[rooms.size()];
        visited[0]=true;
        Stack<Integer> st=new Stack<>();
        st.push(0);
        int count=1;
        while(st.size()>0)
        {
            for(int k: rooms.get(st.pop()))
            {
                if(!visited[k])
                {
                    st.push(k);
                    visited[k]=true;
                    count++;
                }
            }
        }
        if(rooms.size()==count)
            return true;
        return false;
    }
}
