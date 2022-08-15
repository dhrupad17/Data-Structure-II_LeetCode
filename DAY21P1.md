# Sort Characters By Frequency
---
- ## Question:
> Given a string s, sort it in decreasing order based on the frequency of the characters. The frequency of a character is the number of times it appears in the string.
> 
> Return the sorted string. If there are multiple answers, return any of them.
---
- ## Example:
> Input: s = "tree"
> 
> Output: "eert"
---
- ## Solution:
**Code :**
```java
class Solution {
   public String frequencySort(String s) {
	// Count the occurence on each character
	HashMap<Character, Integer> cnt = new HashMap<>();
	for (char c : s.toCharArray()) {
		cnt.put(c, cnt.getOrDefault(c, 0) + 1);
	}
	
	// Sorting
	List<Character> chars = new ArrayList(cnt.keySet());
	Collections.sort(chars, (a, b) -> (cnt.get(b) - cnt.get(a)));

	// Build string
	StringBuilder sb = new StringBuilder();
	for (Object c : chars) {
		for (int i = 0; i < cnt.get(c); i++) {
			sb.append(c);
		}
	}
	return sb.toString();
}
}
