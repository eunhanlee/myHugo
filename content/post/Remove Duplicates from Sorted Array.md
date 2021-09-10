---
title : "Remove Duplicates from Sorted Array"
date : "2021-09-10"
tags : [ProblemSolving,RemoveDuplicatesfromSortedArray]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/ )

## My Answer

- 1 hour limit
- no search on internet

#### My code

```java

class Solution {
    public int removeDuplicates(int[] nums) {
        
        if(nums==null ||nums.length==0) return 0;
        
        int temp = -101;
        int count=0;
        int pos=0;
        
        for(int i=0;i<nums.length;++i){
            if(temp!=nums[i]){
                temp=nums[i];
                nums[pos]=nums[i];
                ++count;
                ++pos;
            }
        }
        
        return count;
        
    }
}
```
- Time complexity : $O(n)$
- Space complexity : $O(1)$

#### My result
- Runtime: 2 ms, faster than 22.76% of Java online submissions for Remove Duplicates from Sorted Array.
- Memory Usage: 45.1 MB, less than 5.23% of Java online submissions for Remove Duplicates from Sorted Array


---

## Best Answer
Search from internet and modify
```java

 class Solution {
    public int removeDuplicates(int[] nums) {
        if(nums==null ||nums.length==0) return 0; //null and 0 check

        int curIndex = 0;
        for (int i = 1; i < nums.length; i++) {
            if (nums[curIndex] != nums[i]) {//if curIndex and loop value is not same
                nums[++curIndex] = nums[i];//insert loop value and move curIndex
            }
        }
        
        return curIndex + 1;//add one for count. CurIndex start from 0
    }
}
```
- Time complexity : $O(n-1)$
- Space complexity : $O(1)$

## Reflect on
- Someone who made this question wanted to test code optimization. My code's algorithm is correct. But it is not optimizated
