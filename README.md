Majority Element
Problem Statement

Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

Example
Example 1
Input: nums = [3,2,3]
Output: 3
Example 2
Input: nums = [2,2,1,1,1,2,2]
Output: 2
Approach

We use Moore’s Voting Algorithm.

Idea
Maintain:
candidate → possible majority element
count → frequency counter
If count becomes 0, choose the current element as the new candidate.
If the current element equals the candidate, increase count.
Otherwise, decrease count.

Since the majority element appears more than n/2 times, it will remain as the final candidate.

C++ Solution
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        
        int count = 0;
        int candidate = 0;

        for(int num : nums) {

            if(count == 0) {
                candidate = num;
            }

            if(num == candidate) {
                count++;
            }
            else {
                count--;
            }
        }

        return candidate;
    }
};
Time Complexity
O(n)
Space Complexity
O(1)
Topics
Arrays
Moore’s Voting Algorithm
Greedy
Repository Name Ideas
majority-element-solution
leetcode-majority-element
moores-voting-algorithm
majority-element-cpp
dsa-majority-element
