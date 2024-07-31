 #leetcode #medium #hashing
### Question
Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** strs = \["eat","tea","tan","ate","nat","bat"\]
**Output:** \[\["bat"],\["nat","tan"],\["ate","eat","tea"\]\]

**Example 2:**

**Input:** strs = \[""\]
**Output:** \[\[""\]\]

**Example 3:**

**Input:** strs = \["a"\]
**Output:** \[\["a"\]\]

**Constraints:**

- `1 <= strs.length <= 104`
- `0 <= strs[i].length <= 100`
- `strs[i]` consists of lowercase English letters.

### Approach
I'm a big fan of this problem as it does a great job of continuing [[LC 242 - Valid Anagram]]. We essentially need a way to uniquely represent a string disregarding it's order and we can do this the same way we did in 242. We'll sort the string and then hash it, we'll then store the string in a hashmap with the key being it's ordered version to group our anagrams together. We can then just iterate through the values of our hashmap to return an answer.

### Code

```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        unordered_map<string, vector<string>> map;
        for(string i: strs){
            string key = i;
            sort(key.begin(), key.end());
            if(!map.contains(key)){
                map[key] = vector<string>{ i };
            }else{
                map[key].push_back(i);
            }
        }
        vector<vector<string>> result;
        for(auto kv: map){
            result.push_back(kv.second);
        }

        return result;
    }
};
```

### Complexity
The complexity of this solution for time is linear as we take a constant number of operations for each element in our input array. For memory complexity it is also linear as we only every store 1 copy of an element in our hashmap. 

### Note on Solution
Big fan of Group Anagrams 😎

### Reference
N/A