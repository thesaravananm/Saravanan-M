# Find Largest Number

This repository contains a Java solution for finding the **largest** element in an array. The solution efficiently determines this value using a single pass through the array.

## Problem Statement
Given an unsorted integer array `arr`, find the **largest** element in the array.

## Intuition
To find the largest element, we traverse the array while keeping track of the maximum value encountered.

## Explanation
1. Initialize `max` with the first element of the array.
2. Iterate through the array:
   - If the current element is greater than `max`, update `max`.
3. Return `max` after traversal.

## Solution
The Java solution uses an efficient approach to solve the problem in **O(n)** time complexity.

### Find Largest Element Implementation
```java
class Solution {
    public static int largest(int[] arr) {
        int max = arr[0];
        for(int i = 0; i < arr.length; i++) {
            if(arr[i] > max) {
                max = arr[i];
            }
        }
        return max;
    }
}
```
