 #leetcode #hashing #easy
### Question
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

**Input:** nums = \[2,7,11,15\], target = 9
**Output:** \[0,1\]
**Explanation:** Because nums\[0\] + nums\[1\] == 9, we return \[0, 1\].

**Example 2:**

**Input:** nums = \[3,2,4\], target = 6
**Output:** \[1,2\]

**Example 3:**

**Input:** nums = \[3,3\], target = 6
**Output:** \[0,1\]

**Constraints:**

- `2 <= nums.length <= 104`
- `-109 <= nums[i] <= 109`
- `-109 <= target <= 109`
- **Only one valid answer exists.**
### Approach
For my first approach I'm going to make a hashmap of int to int mapping the value of a the element to it's position in the array. For every array entry I'll check if target - entry exists in the hashmap. If it does that means we have a match and can return our result. 
### Code

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> map;
        for(int i = 0; i < nums.size(); i++){
            if(map.contains(target - nums[i])){
                return {i, map[target - nums[i]]};
            }
            map[nums[i]] = i;
        }
        return {-1,-1};
    }
};
```

### Complexity
The time complexity of this solution is linear as it performs a constant number of operations for each array element. The memory size is also linear as until a solution is found every element is stored in an array.  

### Note on Solution
You can also solve this with constant memory using a nested for loop, but who really wants to do that, not me!

### Reference
N/A