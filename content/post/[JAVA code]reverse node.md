---
title : "[JAVA code]reverse node"
date : "2021-08-19"
tags : [CodeDictionary, Java, reverse Node, Node, reverse LinkedList, LinkedList]
topics : [CodeDictionary]
---



{{< youtube CvWYBBjAwEg>}}

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

- Time complexity : $O(n)$
- Space complexity : $O(1)$
- input : head node of LinkedList
- output : head node of LinkedList

