---
title : "Fibonacci sequence"
date : "2021-04-12"
tags : [code knowledge, Fibonacci sequence, Fibonacci number, Fibonacci]
topics : [CodeKnowledge]
---

## Definition

Certain patterns of numbers.   
first and second numbers are always 0,1. next number is addition of previous two numbers

## Recurrence Relation

$F_0=0$   
$F_1=1$   
$F_n=F_{n-1}+F_{n-2}$

## Example

| index | fibonacci numbers | calculation |
| ----- | ----------------- | ----------- |
| 0     | 0                 | 0           |
| 1     | 1                 | 1           |
| 2     | 1                 | 0+1         |
| 3     | 2                 | 1+1         |
| 4     | 3                 | 1+2         |
| 5     | 5                 | 2+3         |
| 6     | 8                 | 3+5         |
| 7     | 13                | 5+8         |
| 8     | 21                | 8+13        |
| 9     | 34                | 13+21       |
| 10    | 55                | 21+34       |
| 11    | 89                | 34+55       |
| 12    | 144               | 55+89       |
| 13    | 233               | 89+144      |
| 14    | 377               | 144+233     |
| 15    | 610               | 233+377     |
| 16    | 987               | 377+610     |

## get nth fibonacci number

### Repeat

```java
unsigned int fibonacci_iter(unsigned int n) {

    if (n == 0) return 0;
    else if (n == 1) return 1;
    else {

        int result = 0;
        int iterA = 0;
        int iterB = 1;

        for (int i = 2; i <= n; i++) {

            result = iterA + iterB;
            iterA = iterB;
            iterB = result;

        }

        return result;

    }

}
```

### recuresive

```java
unsigned int fibonacci_rcsv(unsigned int n) {

    if (n == 0) return 0;
    else if (n == 1) return 1;
    else return fibonacci_rcsv(n - 2) + fibonacci_rcsv(n - 1);

}
```

### math

```java
public int fib(int N) {
        double goldenRatio = (1 + Math.sqrt(5)) / 2;
        return (int)Math.round(Math.pow(goldenRatio, N)/ Math.sqrt(5));
}
```

## verify fiboncci number

A number is Fibonacci if and only if one or both of $(5n^2+4)$ or $(5n^2-4)$ is a perfect square

### perfect square

when x is $\sqrt{x} \cdot \sqrt{x}=x$   
The $\sqrt{x}$ must not decimal number.

```java
    static boolean isPerfectSquare(int x) {
        int s = (int) Math.sqrt(x);
        return (s * s == x);
    }

    static boolean isFibonacci(int n) {
        return isPerfectSquare(5 * n * n + 4) || isPerfectSquare(5 * n * n - 4);
    }
```
