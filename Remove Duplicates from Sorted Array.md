# Remove Duplicates from Sorted Array

This repository contains a Java solution for removing duplicates from a sorted array. The solution modifies the input array in place and returns the new length of the array after removing duplicates.

## Problem Statement
Given an integer array `nums` sorted in non-decreasing order, remove the duplicates **in-place** such that each unique element appears only once. The relative order of elements should be kept the same.

Return the number of unique elements. The first `k` elements of `nums` should hold the unique elements, and the rest of `nums` does not matter.

## Intuition
Since the array is already sorted, duplicate elements will always be adjacent to each other. By using a **two-pointer approach**, we can efficiently shift unique elements forward without needing extra space. This allows us to modify the array in-place while maintaining the relative order of elements.

## Explanation
1. We initialize a pointer `j` to track the position of unique elements.
2. We iterate through the array starting from the second element (index `1`).
3. If the current element is different from the previous element, it means we have found a unique element.
4. We place this unique element at position `j` and increment `j`.
5. After processing the array, `j` represents the count of unique elements, which is returned as the result.

## Solution
The Java solution uses a two-pointer approach to efficiently remove duplicates in **O(n)** time complexity.

### Implementation
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int j = 1;
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] != nums[i - 1]) {
                nums[j] = nums[i];
                j++;
            }
        }
        return j;
    }
}
```
