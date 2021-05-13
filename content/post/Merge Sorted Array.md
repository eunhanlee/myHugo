---
title : "Merge Sorted Array"
date : "2021-05-13"
tags : [algorithm problem solving, Merge Sorted Array]
topics : [ProblemSolving]
---


## Problem

[Problem_Link](https://leetcode.com/problems/merge-sorted-array/){: .btn .btn-green}

- 1 hour limit
- no search on internet
  Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

The number of elements initialized in nums1 and nums2 are m and n respectively. You may assume that nums1 has a size equal to m + n such that it has enough space to hold additional elements from nums2.

#### Example 1:

Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]

#### Example 2:

Input: nums1 = [1], m = 1, nums2 = [], n = 0
Output: [1]

#### Constraints:

nums1.length == m + n
nums2.length == n
0 <= m, n <= 200
1 <= m + n <= 200
$-10^9$ <= nums1[i], nums2[i] <= $10^9$

## My Answer

### Overview

- condition will be m and n
- since length is provided, it should be backward
- other constraints means int type range

### My code

```java
class Solution {
        public void merge(int[] nums1, int m, int[] nums2, int n) {

        int i = m+n-1;
        m--;
        n--;

        while(m >=0 && n>=0)
		{
			if(nums1[m] > nums2[n])
				nums1[i--] = nums1[m--];
			else
				nums1[i--] = nums2[n--];
		}

        while(n >= 0)
			nums1[i--] = nums2[n--];

        }
    }
```

### My result

Runtime: 0 ms, faster than 100.00% of Java online submissions for Merge Sorted Array.
Memory Usage: 38.8 MB, less than 89.83% of Java online submissions for Merge Sorted Array.

## Reflect on

- my answer is exactly same from discussion. However, I had to think too long and did no thave enough time to code
- I need to think like computer.

## Other Answers

```
public:
    void merge(int A[], int m, int B[], int n) {
        int i=m-1;
		int j=n-1;
		int k = m+n-1;
		while(i >=0 && j>=0)
		{
			if(A[i] > B[j])
				A[k--] = A[i--];
			else
				A[k--] = B[j--];
		}
		while(j>=0)
			A[k--] = B[j--];
    }
};
```

## Additional Study needed
