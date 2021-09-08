---
title : "Two Sum"
date : "2021-09-08"
tags : [ProblemSolving,TwoSum]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/two-sum/)

## My Answer

- 1 hour limit
- no search on internet

### Overview

- input : int[] nums, int target
- output : int[]

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

- Time complexity : $O(n^2)$
- Space complexity : $O(1)$

### My result

Runtime: 76 ms, faster than 12.73% of Java online submissions for Two Sum.

Memory Usage: 41.9 MB, less than 16.55% of Java online submissions for Two Sum.

---

## Best Answer

Search from internet and modified

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

- I solved with Brute Force Algorithm. This is not wrong. However, hash map is more efficient.

## Additional Study needed

- IllegalArgumentException (exceptions)
- hash
