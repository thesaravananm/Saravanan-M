# Check if Array is Sorted and Rotated

This repository contains a Java solution to check whether a given array is sorted and rotated.

## Problem Statement
Given an integer array `nums`, determine if it can become non-decreasing by rotating it some number of positions.

## Intuition
An array that is sorted and rotated will have at most **one** inversion (where `nums[i] > nums[i+1]`). If there is more than one inversion, the array is not sorted and rotated.

## Explanation
1. Initialize a `count` variable to track the number of inversions.
2. Iterate through the array:
   - If `nums[i] > nums[(i + 1) % n]`, increment `count`.
   - If `count` exceeds 1, return `false`.
3. Return `true` if `count` is 0 or 1.

## Solution
The Java solution uses an efficient approach to solve the problem in **O(n)** time complexity.

### Check if Array is Sorted and Rotated Implementation
```java
class Solution {
    public boolean check(int[] nums) {
        int count = 0;
        int n = nums.length;
        
        for (int i = 0; i < n; i++) {
            if (nums[i] > nums[(i + 1) % n]) {
                count++;
            }
            if (count > 1) return false; 
        }
        
        return true;
    }
}
```
