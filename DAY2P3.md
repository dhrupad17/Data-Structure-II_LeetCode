# Design HashMap
---
- ## Question:
> Design a HashMap without using any built-in hash table libraries.
---
- ## Example:
> Input
> 
>["MyHashMap", "put", "put", "get", "get", "put", "get", "remove", "get"]
>
> [[], [1, 1], [2, 2], [1], [3], [2, 1], [2], [2], [2]]
> 
> Output
> 
> [null, null, null, 1, -1, null, 1, null, -1]
---
- ## Solution:
**Code :**
```java
class MyHashMap {
    int[] map;
    public MyHashMap() {
        map=new int[1000000+1];
    }
    
    public void put(int key, int value) {
        map[key]=value+1;
    }
    
    public int get(int key) {
        return map[key]-1;
    }
    
    public void remove(int key) {
        map[key]=0;
    }
}
