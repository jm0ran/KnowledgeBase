 #leetcode #easy #hashing
### Question
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

**Input:** nums = \[1,2,3,1\]
**Output:** true

**Example 2:**

**Input:** nums = \[1,2,3,4\]
**Output:** false

**Example 3:**

**Input:** nums = \[1,1,1,3,3,4,3,2,4,2\]
**Output:** true

**Constraints:**

- `1 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`

### Approach
To solve this in linear time we'll just use a hash set and iterate over the array. For each element we'll first check if it exists in the hash set. If it doesn't, add it and move on, if it does, break and return true as a duplicate has been verified.
### Code
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> intSet;
        for(int num: nums){
            if(intSet.contains(num)){
                return true;
            }
            intSet.insert(num);
        }
        return false;
    }
};
```

### Complexity
The time complexity of this solution is linear as we simply iterate over the array. In the same way the memory complexity is linear as one entry is made int he set for each element.

### Note on Solution
N/A

### Reference
N/A