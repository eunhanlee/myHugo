---
title : "Merge Two Sorted Lists"
date : "2021-04-16"
tags : [algorithm problem solving, Merge Two Sorted Lists]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/merge-two-sorted-lists/){: .btn .btn-green}

- 1 hour limit
- no search on internet

Merge two sorted linked lists and return it as a **sorted** list. The list should be made by splicing together the nodes of the first two lists.

**Example 1:**
```
Input: l1 = [1,2,4], l2 = [1,3,4]
Output: [1,1,2,3,4,4]

```

**Example 2:**

```
Input: l1 = [], l2 = []
Output: []

```

**Example 3:**

```
Input: l1 = [], l2 = [0]
Output: [0]

```

**Constraints:**

- The number of nodes in both lists is in the range `[0, 50]`.
- `100 <= Node.val <= 100`
- Both `l1` and `l2` are sorted in **non-decreasing** order.

## My Answer

### My code

```java
class Solution {
    public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
        if (l1 == null) {
            return l2;
        }
        if (l2 == null) {
            return l1;
        }

        ListNode head = new ListNode(-101);
        ListNode prev = head;

        while (l1 != null && l2 != null) {
            if (l1.val <= l2.val) {
                prev.next = l1;
                l1 = l1.next;
            } else {
                prev.next = l2;
                l2 = l2.next;
            }
            prev = prev.next;
        }

	prev.next = l1 == null ? l2 : l1;
        return head.next;

    }
}
```

### My result

Runtime: 0 ms, faster than 100.00% of Java online submissions for Merge Two Sorted Lists.
Memory Usage: 38 MB, less than 95.72% of Java online submissions for Merge Two Sorted Lists.

## Reflect on

- could not solve in an hour
- did not consider recursion at all.
- algorithm seems correct but spent too much time to find other answer that does not exist
- missed last case (prev.next = l1 == null ? l2 : l1;)

## Additional Study needed
