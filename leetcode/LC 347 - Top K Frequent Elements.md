 #leetcode #medium #hashing #returnto
### Question
Given an integer array nums and an integer k, return the k most frequent elements. You may return the answer in any order.

Example 1:
Input: nums = \[1,1,1,2,2,3\], k = 2
Output: \[1,2\]
Example 2:
	Input: nums = \[1\], k = 1
	Output: \[1\]
 
Constraints:
- 1 <= nums.length <= 105
- -104 <= nums\[i\] <= 104
- k is in the range \[1, the number of unique elements in the array\].
- It is guaranteed that the answer is unique.
 
Follow up: Your algorithm's time complexity must be better than O(n log n), where n is the array's size.

### Approach
The first step of this problem is relatively straight forward as a hashmap can just be used to map integer values to their frequencies after iterating through the vector of nums. The trickier part comes when we want to use this information. The main question is how to sort the hashmap by frequency of elements. While in Java I'd make a comparator class and sort a list with it. I'm not that comfortable with C++ at the moment so my initial attempt will be to use a bucket sort to organize our data. Then I'll simply iterate backwards over the array until we collect k elements and have our result.

### Code
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        // First make a map of the values in the nums array and their frequencies
        unordered_map<int, int> hashMap;
        for(int num: nums){
            if(!hashMap.contains(num)){
                hashMap[num] = 1;
            }else{
                hashMap[num]++;
            }
        }

        // Now we'll get it all into an array indexed by frequency with list values in each entry
        list<int> frequencies[nums.size() + 1];

        // Now group them by frequency
        for(auto kv: hashMap){
            frequencies[kv.second - 1].push_back(kv.first);
        }

        // Finally, build our result
        vector<int> result;
        int i = nums.size(); //Start at index 6 while looking
        while(k > 0){
            if(frequencies[i].size() == 0){
                i--;
            }else{
                result.push_back(frequencies[i].back());
                frequencies[i].pop_back();
                k--;
            }
        }
        
        // Return our resulting array
        return result;
    }
};
```

### Complexity
The time complexity of this solution is linear and will remain linear but I do feel that sorting the results of the hashmap in the end could be more efficient than bucket sort. I also feel that memory usage while also linear could be significantly improved without all the overhead of a list in each spot of our frequencies array.

### Note on Solution
I would like to come back to this at some point and implement a list sorting solution, but time will tell if that happens.

### Reference
N/A