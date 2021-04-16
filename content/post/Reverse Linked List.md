---
title : "Reverse Linked List"
date : "2021-04-16"
tags : [algorithm problem solving, Reverse Linked List]
topics : [ProblemSolving]
---
## Problem

[Problem_Link](https://leetcode.com/problems/reverse-linked-list/)

- 1 hour limit
- no search on internet


Reverse a singly linked list.

**Example:**

```
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?

## My Answer

### My code

```java
class Solution {
     public ListNode reverseList(ListNode head) {


        Stack<ListNode> stack = new Stack<>();

        while (head != null) {
            stack.push(head);
            head = head.next;

        }

        ListNode rtnHead = new ListNode();
        ListNode temp = rtnHead;

        while (!stack.isEmpty()) {
            temp.next = stack.pop();
            temp = temp.next;
        }
        temp.next=null;


        return rtnHead.next;
    }
}
```

### My result

Runtime: 1 ms, faster than 5.56% of Java online submissions for Reverse Linked List.
Memory Usage: 38.7 MB, less than 65.68% of Java online submissions for Reverse Linked List.

## Reflect on

- I believe that question should have more explaination.
- I'm tend to do not change the input data structure. According to leetcode answer of Iterative, it revese the input node. on the other hand, my code keep data in stack and reverse it.
- For recursive, I could not build in an hour, Thus, just check the answer. I need to study recursion more.

## Other Answers

#### Iterative

```
public ListNode reverseList(ListNode head) {
    ListNode prev = null;
    ListNode curr = head;
    while (curr != null) {
        ListNode nextTemp = curr.next;
        curr.next = prev;
        prev = curr;
        curr = nextTemp;
    }
    return prev;
}

```

#### Iterative process
![](https://raw.githubusercontent.com/eunhanlee/img/main/0015.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0016.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0017.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0018.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0019.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0020.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0021.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0022.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0023.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0024.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0025.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0026.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0027.png)


**Complexity analysis**

- Time complexity : $O(n)$
- Space complexity : $O(1)$

#### Recursive

```
public ListNode reverseList(ListNode head) {
    if (head == null || head.next == null) return head;
    ListNode p = reverseList(head.next);
    head.next.next = head;
    head.next = null;
    return p;
}
```

#### Recursive process
![](https://raw.githubusercontent.com/eunhanlee/img/main/0028.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0029.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0030.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0031.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0032.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0033.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0034.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0035.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0036.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0037.png)
![](https://raw.githubusercontent.com/eunhanlee/img/main/0038.png)


**Complexity analysis**

- Time complexity : $O(n)$
- Space complexity : $O(n)$

## Additional Study needed
