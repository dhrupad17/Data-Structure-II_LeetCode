# Repeated DNA Sequences
---
- ## Question:
> Given a string s that represents a DNA sequence, return all the 10-letter-long sequences (substrings) that occur more than once in a DNA molecule. You may return the answer in any order.
---
- ## Example:
> Input: s = "AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT"
> 
> Output: ["AAAAACCCCC","CCCCCAAAAA"]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<String> findRepeatedDnaSequences(String s) {
        HashMap<String,Integer> map =new HashMap();
        int i=0;
        int j=0;
        int k=10;
        StringBuilder sb=new StringBuilder("");
        
        while(j<s.length()){
            sb.append(s.charAt(j));
            if(j-i+1<k){
                j++;
            }else if(j-i+1==k){
                if(!map.containsKey(sb.toString())){
                    map.put(sb.toString(),1);
                }else{
                    map.put(sb.toString(),map.get(sb.toString())+1);
                }
                sb.deleteCharAt(0);
                i++;
                j++;
            }
        }
        List<String> list=new ArrayList();
        for(Map.Entry<String,Integer> mapElement:map.entrySet()){
            if(mapElement.getValue()>1){
                list.add(mapElement.getKey());
            }
        }
        return list;
    }
}
