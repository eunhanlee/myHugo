---
title : "Count Binary Substrings"
date : "2021-09-08"
tags : [ProblemSolving,Count Binary Substrings]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/count-binary-substrings/ )

## My Answer

- 1 hour limit
- no search on internet
### My result
```
Compile Error
```
## Best Answer
Search from internet and modify
```java

class Solution {    
        public int countBinarySubstrings(String s) {
        int curRun = 1;
        int preRun = 0;
        int count = 0;
        
        for (int i = 1; i < s.length(); i++) {
            if (s.charAt(i) == s.charAt(i - 1)) ++curRun;
            else {
                count += Math.min(curRun, preRun);
                preRun = curRun;
                curRun = 1;
            }
        }
        return count + Math.min(curRun, preRun);
    }
}
```
- Time complexity : $O(n)$
- Space complexity : $O(1)$


## Reflect on
- It count how many same numbers and compare previous and current one. then, pick smaller one. add them up.
- for 0001111, first will be 3 and second will be 4, answer will be 3 (01,0011,000111)->(3,4)-min->3
- fail to find the algorithm on time. I started to wrong way. Trying to use stack and compare.