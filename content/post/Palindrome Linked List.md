---
title : "Palindrome Linked List"
date : "2021-05-06"
tags : [algorithm problem solving, Palindrome Linked List]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/palindrome-linked-list/)

- 1 hour limit
- no search on internet

Given a singly linked list, determine if it is a palindrome.

**Example 1:**

```
Input: 1->2
Output: false
```

**Example 2:**

```
Input: 1->2->2->1
Output: true
```

**Follow up:**Could you do it in O(n) time and O(1) space?

## My Answer

### Overview

- palindrome, this is same front and back.
- only need to verify this is palindrome or not
- O(n) time and O(1) space limited
- since this is linkedlist, cannot check by the length/2
- using stack would be easier but it will not be O(1) space.

### My code

```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public boolean isPalindrome(ListNode head) {
        if(head==null) return true;
        else if(head.next==null) return true;
        else if(head.next.next==null){
            if(head.val==head.next.val) return true;
            else return false;
        }

        int len = 3;
        ListNode prevhead=head.next;
        prevhead.next=head;
        head.next=null;
        head=prevhead.next;

        while(head.next!=null){

            if(head.val == head.next.val){
                prevhead=head;
                head=head.next;
                break;
            }

            ListNode temphead=head.next;
            head.next=prevhead;
            prevhead=head;
            head=temphead;
            len++;
        }

        while(head.next!=null){
            if(prevhead.next==null) return false;
            if(head.val != prevhead.val) return false;

            head=head.next;
            prevhead=prevhead.next;
            len++;

        }

        if(len%2 != 0) return false;
        return true;
    }
}
```

### My result

Wrong Answer

## Reflect on

- basic algorithm was same as the discussion answer. However, I had struggle with detailed edge cases such as checking palindrome with one value in the linkedlist.
- Recursive (Advanced) answer is nice to study. I believe that is not good for teamwork.


## Additional Study needed
