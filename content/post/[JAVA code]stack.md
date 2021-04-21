---
title : "[JAVA code]stack"
date : "2021-04-21"
tags : [Java Dictionary,Stack]
topics : [Java]
---

```java

private Stack<Integer> stack;
this.stack = = new Stack<>(); 
```

```java

Stack<Integer> stack = new Stack<>(); //int type stack
stack.push(1);     // add value
stack.pop();       // remove value and return the value of top
stack.clear();     // remove all value
stack.peek();     // return the value of top
stack.size();      
stack.empty();     // check the stack is empty(if empty true)
stack.contains(1) // check the value 1 is in stack (if there, true) worst O(n)
```
