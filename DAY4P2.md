# Non-overlapping Intervals
---
- ## Question:
> Given an array of intervals intervals where intervals[i] = [starti, endi], return the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.
---
- ## Example:
> Input: intervals = [[1,2],[2,3],[3,4],[1,3]]
> 
> Output: 1
> 
> Explanation: [1,3] can be removed and the rest of the intervals are non-overlapping.
---
- ## Solution:
**Code :**
```java
class Solution {
    public int eraseOverlapIntervals(int[][] intervals) {
        if(intervals.length==0|| intervals==null)
            return 0;
        int count=0;
        Arrays.sort(intervals, (a, b) -> Integer.compare(a[1], b[1]));
        int prevEnd=intervals[0][1];
        for(int i=1;i<intervals.length;i++)
        {
            if(intervals[i][0]<prevEnd)
            {
                count++;
            }
            else
            {
                prevEnd=intervals[i][1];
            }
        }
        return count;
    }
}
