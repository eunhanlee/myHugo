---
title : "Kadane's Algorithm"
date : "2021-04-19"
tags : [code knowledge, Kadane's Algorithm]
topics : [CodeKnowledge]
---

## Purpose

Find maximum sum of contiguous values in an array. The array order must not change.

## Example

If there is $[-2, 1, -3, 4, -1, 2, 1, -5, 4] $  
$[4, -1, 2, 1]$ is the answer   
4+(-1)+2+1=6, this is bigger than any other contiguous values.

## Complexity Analysis

* Time complexity : $O(N)$ since it's one pass along the array.
* Space complexity : $O(1)$, since it's a constant space solution.

## Explanation

For finding maxium number, we need to calculate all of possible numbers and compare.
for array of {2,-1,6,-3}, all of possible numbers are:

- 2
- 2,-1
- 2,-1,6
- 2,-1,6,-3
- -1
- -1,6
- -1,6,-3
- 6
- 6,-3
- -3

We can notice that subarray \[2,-1,6,-3\] is duplicated with subarray\[2,-1,6\]
In other ward, we do no need to calculate both \[2+(-1)+6+(-3)\] and \[2+(-1)+6\]
We can calculate \[2+(-1)+6\] and \[2+(-1)+6\]+(-3). Thus, we can skip the duplicated part.

## example

If there are {2,-1,6,-3}, we need to calculate all of possible addition and compare, pick the maxium number.

![](https://raw.githubusercontent.com/eunhanlee/img/main/0000.png)

Thus, maxium addition number of possible sets are the answer as table
in Kadane's Algorithm, we compare the current one and added previous sum and current one.
It only compare what it needed

## example of process

![](https://raw.githubusercontent.com/eunhanlee/img/main/0001.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0002.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0003.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0004.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0005.png)


## improvement

Since temp array contain the sum for previous numbers and we do not need them, we can put the sum data in the same input array. In this way, we can save some memory.

## Math

$K_i=max(arr[i],k_{i-1}+arr[i])$

## Final code

```java
class Solution {
    public int maxSubArray(int[] nums) {
        int max=Integer.MIN_VALUE;
        for (int i = 1; i < nums.length; i++) {
            if(max < Math.max(nums[i], nums[i] + nums[i - 1]))
                max=Math.max(nums[i], nums[i] + nums[i - 1]);

            nums[i] = Math.max(nums[i], nums[i] + nums[i - 1]);
        }
        return max;

    }
}
```

