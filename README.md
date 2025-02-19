# experiment-no.-4-22BCS_IOT-701B
https://leetcode.com/problems/longest-nice-substring/description/
class Solution {
public:
    string longestNiceSubstring(string s) {
        if (s.size() < 2)
            return "";
        
        unordered_set<char> st(s.begin(), s.end());
        for (int i = 0; i < s.size(); i++) {
            if (st.count(tolower(s[i])) && st.count(toupper(s[i])))
                continue;
            
            string left = longestNiceSubstring(s.substr(0, i));
            string right = longestNiceSubstring(s.substr(i + 1));
            return left.size() >= right.size() ? left : right;
        }
        return s;
        
    }
};


https://leetcode.com/problems/maximum-subarray/description/

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxSum = nums[0];  // Stores the maximum sum
        int currentSum = 0;    // Stores the current subarray sum

        for (int num : nums) {
            // If currentSum is negative, reset it to 0
            if (currentSum < 0) 
                currentSum = 0;

            // Add current element to currentSum
            currentSum += num;

            // Update maxSum if we found a new max
            maxSum = max(maxSum, currentSum);
        }

        return maxSum; // Return the maximum subarray sum
    }
};

Experiment no. 4
