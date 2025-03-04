# Find Second Largest Number

This repository contains a Java solution for finding the second-largest element in an array. The solution efficiently determines the second-largest number using a single pass through the array.

## Problem Statement
Given an unsorted integer array `arr`, find the **second-largest** element in the array. If there is no second-largest element, return `-1`.

## Intuition
To determine the second-largest element efficiently, we track both the largest and second-largest values while iterating through the array. If a new maximum is found, the previous maximum becomes the second-largest. If a value is less than the maximum but greater than the second-largest, it updates the second-largest.

## Explanation
1. Initialize `max` and `secondmax` to `-1`.
2. Iterate through the array:
   - If the current element is greater than `max`, update `secondmax` to `max`, then update `max`.
   - If the current element is between `max` and `secondmax`, update `secondmax`.
3. Return `secondmax` after traversal.

## Solution
The Java solution uses an efficient approach to solve the problem in **O(n)** time complexity.

### Implementation
```java
class Solution {
    public int getSecondLargest(int[] arr) {
        int max = -1;
        int secondmax = -1;
        int n = arr.length;
        for (int i = 0; i < n; i++) 
        {
            if (max < arr[i]) 
            {
                secondmax = max;
                max = arr[i];
            } 
            else if (secondmax < arr[i] && arr[i] < max)
            {
                secondmax = arr[i];
            }
        }     
        return secondmax;
    }
}
```
