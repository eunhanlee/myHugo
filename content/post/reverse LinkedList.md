---
title : "reverse node"
date : "2021-04-02"
tags : [Java Dictionary, reverse ListNode, ListNode, reverse LinkedList, LinkedList]
topics : [Java]
katex: true
markup: "mmark"
---

```java
public static ListNode reverse(ListNode head) {
    ListNode prev = null;
    while (head != null) {
        ListNode next = head.next;
        head.next = prev;
        prev = head;
        head = next;
    }
    return prev;
}
```