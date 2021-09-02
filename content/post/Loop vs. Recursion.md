---
title : "Loop vs. Recursion"
date : "2021-09-02"
tags : [CodeStudy,Recursion,Loop]
topics : [CodeStudy]
---


### Definition
Saperate big problem into small repeated parts and solve the problem.

All Recursion can be converted to Loop.

### Good and bad points
|Loop|Recursion|
|---|---|
|intuitive|complicated|
|Long codes|short codes|
|good readability|bad readability|
|use less stack memories|use much stack memories|
|very low possiblity to get Stack overflow|Stack overflow if too mcuh call|
|very low possiblity to get overhead issue|overhead issue: call function repeatly will make program slow
|each level of variable state will not saved|each level of variable state will saved because of stack|


### Actual code
We should write recursion because it is good for reading and fixing it.

#### However, we need to use loop when..
- input may cause stack overflow : If the program need to calculate huge number of Fibonacci sequence
- the program need to be fast : call loop function 10 million times in 1 second.
