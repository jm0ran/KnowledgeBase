 #leetcode #easy #hashing
### Question
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** s = "anagram", t = "nagaram"
**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"
**Output:** false

**Constraints:**

- `1 <= s.length, t.length <= 5 * 104`
- `s` and `t` consist of lowercase English letters.

### Approach
If I want to solve this in linear time I am going to need a way to compare the two strings disregarding the order of characters. I see two ways of doing this. The first is to create a hash map of characters to ints adding 1 for character occurrence in the first word and subtracting in the second. The goal would be a hashmap with values of 0 for every character. The second solution would be to sort the strings alphabetically and then compare them.

### Code
**HashMap Solution**
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        unordered_map<char, int> charMap;
        
        // First string
        for(char i: s){
            if(!charMap.contains(i)){
                charMap[i] = 1;
            }else{
                charMap[i] = charMap.at(i) + 1;
            }
        }
        
        // Second String
        for(char i: t){
            if(!charMap.contains(i)){
                return false;
            }else{
                if(charMap.at(i) == 1){
                    charMap.erase(i);
                }else{
                    charMap[i] = charMap.at(i) - 1;
                }
            }
        }
        
        // If charmap size is 0, string is an anagram
        return charMap.size() == 0;
    }
};
```

**Sorting Solution**
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        // Sort the two strings
        sort(s.begin(), s.end());
        sort(t.begin(), t.end());
        //Compare
        return s == t;
    }
};
```
### Complexity
The time complexity of both solutions is linear. The memory complexity on the hashmap solution is linear while on the sorting solution is constant assuming that we perform the entire operation in place.

### Note on Solution
While I started with the hashmap solution and do kind of like it, the sorting solution is quicker, uses less memory (assuming we are allowed to sort these strings in place), and is much simpler to read and write.

### Reference
N/A