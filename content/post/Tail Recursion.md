---
title : "Tail Recursion"
date : "2021-09-02"
tags : [CodeStudy,Recursion,TailRecursion,Loop]
topics : [CodeStudy]
---


## Definition

A method of recursion optimization

### Principle
When there is recursion, the recursive class remain in stack memory and it will cause overflow. The tail call elimination is created for fixing the overflow issue. If the reucursive class return everything at last, the class does need to remain in stack memory.

#### Other Names
- tail call elimination
- tail call optimization

### How to

Change return part of recursion to call function only.
Return should not contain any operation.

### Compiler
Since tail recursion is depend on compiler, computer language need to support 
- Java: No
- Kotlin: Yes
- C++: Yes
- C : Yes
- C# : Yes
- Swift : Yes
- goLang: No

### Example-factorial calculation, Kotlin
```Kotlin

fun main() {
    println(TailFactorialRecursive(5, 1))
    println(NormalFactorialRecursive(5))
}

tailrec fun TailFactorialRecursive(n: Int, sum: Int): Int {
    if (n == 1) {
        return sum
    }
    return TailFactorialRecursive(n - 1, n * sum)
}


fun NormalFactorialRecursive(n: Int): Int {
    if (n == 1) {
        return 1
    }
    return n * NormalFactorialRecursive(n - 1)
}
```

### Explaination

For the NormalFactorialRecursive, the recursive class have to wait for calculating `n * NormalFactorialRecursive(n - 1)`
For the TailFactorialRecursive, the recursive class do not need to wait for calculating `FactorialRecursive(n - 1, n * sum)`
