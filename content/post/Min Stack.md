---
title : "Min Stack"
date : "2021-05-04"
tags : [algorithm problem solving, Min Stack]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/min-stack/)

- 1 hour limit
- no search on internet
  

Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.
- push(x) -- Push element x onto stack.
- pop() -- Removes the element on top of the stack.
- top() -- Get the top element.
- getMin() -- Retrieve the minimum element in the stack.

**Example 1:**

```
Input
["MinStack","push","push","push","getMin","pop","top","getMin"]
[[],[-2],[0],[-3],[],[],[],[]]

Output
[null,null,null,null,-3,null,0,-2]

Explanation
MinStack minStack = new MinStack();
minStack.push(-2);
minStack.push(0);
minStack.push(-3);
minStack.getMin(); // return -3
minStack.pop();
minStack.top();    // return 0
minStack.getMin(); // return -2

```

**Constraints:**

- Methods `pop`, `top` and `getMin` operations will always be called on **non-empty** stacks.

## My Answer

### Overview

- create stack class

### My code

```java
class MinStack {

    /** initialize your data structure here. */
    int minValue = Integer.MAXVALUE;
    public MinStack() {
        Linkedlist head= new Linkedlist();
    }

    public void push(int x) {
        Linkedlist new= new Linkedlist(x);

        if(head.next!=null){
            Linkedlist temp;
            temp=head.next();
            while(temp.next()!=null;)
                temp=temp.next();
            temp.next()=new;

        }else
            head.next()=new;

        if(x<minValue) minValue=x;
    }

    public void pop() {
        if(head.next()!=null && head.next().next() !=null){
            Linkedlist temp=head.next().next();
            head.next().next()=null;
            head.next()=temp;
        }else if(head.next()!=null){
            head.next()=null;
        }

    }

    public int top() {
        return head.next().value;
    }

    public int getMin() {
        return minValue;
    }
}

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack obj = new MinStack();
 * obj.push(x);
 * obj.pop();
 * int param_3 = obj.top();
 * int param_4 = obj.getMin();
 */
```

### My result

Compile Error

## Reflect on

- I have learned about stack, LinkedList and other data structures. However, I never build one from scratch. I believed that is meaningless because we always have internet. Now, I realized that I need to study for that part.
- The answers in the website have two separate ways. First one is that question wanted to build stack data structure from scratch and second one is that take care the min value with stack. I am not sure which one is correct. Thus, I will study both.

## Other Answers

- stack created by LinkedList node

  ```java
  class MinStack {
      private Node head;

     public void push(int x) {
      if(head == null)
          head = new Node(x, x, null);
      else
          head = new Node(x, Math.min(x, head.min), head);
  }

  public void pop() {
      head = head.next;
  }

  public int top() {
      return head.val;
  }

  public int getMin() {
      return head.min;
  }

  private class Node {
      int val;
      int min;
      Node next;

      private Node(int val, int min, Node next) {
          this.val = val;
          this.min = min;
          this.next = next;
      }
  }
  }
  ```


## Additional Study needed

- building data structure from scratch
- learning custom stack
