---
title : "tail call elimination"
date : "2021-04-21"
tags : [code knowledge, tail call elimination,tail call optimization,tail recursion]
topics : [CodeKnowledge]
---

## Definition

When there is recursion, the recursive class remain in stack memory and it will cause overflow. The tail call elimination is created for fixing the overflow issue. If the reucursive class return everything at last, the class does need to remain in stack memory.

### Other Names

- tail call elimination
- tail call optimization

### tail call elimination providers

Currently(4/21/2021), some languages provide this function and some are not.

- Java: No.
- Kotlin: Yes. with additional keyword
- C++: Yes
- goLang: No.

### Example

Kotlin

```Kotlin

fun main() {
    println(FactorialRecursive(5, 1))
    println(NormalFactorialRecursive(5))
}

tailrec fun FactorialRecursive(n: Int, sum: Int): Int {
    if (n == 1) {
        return sum
    }
    return FactorialRecursive(n - 1, n * sum)
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

For the FactorialRecursive, the recursive class do not need to wait for calculating `FactorialRecursive(n - 1, n * sum)`
