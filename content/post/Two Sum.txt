---
title : "Two Sum"
date : "2021-03-31"
tags : []
topics : [Algorithm Questions]
description : ""
---

## Problem

[Problem_Link](https://leetcode.com/problems/two-sum/)

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to `target`*.

You may assume that each input would have ***exactly* one solution**, and you may not use the *same* element twice.

You can return the answer in any order.

**Example 1:**

```
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```
Input: nums = [3,3], target = 6
Output: [0,1]
```

**Constraints:**

- `2 <= nums.length <= 103`
- `109 <= nums[i] <= 109`
- `109 <= target <= 109`
- Only one valid answer exists.

## My Answer

- 1 hour limit
- no search on internet

### My code

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
                int temp[] = new int[nums.length];
        int rtn[] = new int[2];
        for (int i = 0; i < nums.length; i++) {
            temp[i] = target - nums[i];
            for (int j = 0; j < i; j++) {

                if (temp[j] == nums[i]) {

                    rtn[0] = j;
                    rtn[1] = i;

                    return rtn;

                }
            }

        }

        rtn[0] = 0;
        rtn[1] = 0;
        return rtn;


    }
}
```

### My result

```
Runtime: 0 ms
Memory Usage: 39.5 MB
```

## Best Answer

Search from internet and other people to create best code

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int tempkey = target - nums[i];

            if (map.containsKey(tempkey)) {
                return new int[] { map.get(tempkey), i };
            }

            map.put(nums[i], i);
        }

        throw new IllegalArgumentException("No solution");
    }
}
```

- Time complexity : $O(n)$
- Space complexity : $O(n)$

## Reflect on

- Have no idea about "IllegalArgumentException" I knew this is there but did not know what representing.
- basic algorithm was correct and good as answers from solution. However, I did not use the hash table even though I know that data structure and it's O(n). I need to used to use the other data structures.

## Additional Study needed

- IllegalArgumentException (exceptions)
- hash table
