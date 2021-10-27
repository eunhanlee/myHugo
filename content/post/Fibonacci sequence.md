---
title : "Fibonacci sequence"
date : "2021-10-27"
tags : [CodeStudy, FibonacciSequence, FibonacciNumber, Fibonacci]
topics : [CodeStudy]
---

## Definition

Certain patterns of numbers.   
first and second numbers are always 0,1. next number is addition of previous two numbers

## The List of Fibonacci numbers

$0,1,1,2,3,5,8,13,21,34,55...$

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

### math

```java

    public static int fib(int num) {
        double goldenRatio = (1 + Math.sqrt(5)) / 2;
        return (int) Math.round(Math.pow(goldenRatio, num) / Math.sqrt(5));
    }
```

### recuresive

```java

    public static int fibRecursive(int num) {
        if (num == 0) return 0;
        else if (num == 1) return 1;
        else return fibRecursive(num - 2) + fibRecursive(num - 1);
    }
```

### Repeat

```java

    public static int fib(int num) {
        if (num == 0) return 0;
        else if (num == 1) return 1;

        else {
            int result = 0;
            int iterA = 0;
            int iterB = 1;

            for (int i = 2; i <= num; i++) {

                result = iterA + iterB;
                iterA = iterB;
                iterB = result;

            }

            return result;
        }

    }
```

## verify fiboncci number

A number is Fibonacci if and only if one or both of $(5n^2+4)$ or $(5n^2-4)$ is a perfect square

### perfect square

when x is $\sqrt{x} \cdot \sqrt{x}=x$   
The $\sqrt{x}$ must not decimal number.


### Example Code

```java

    public static boolean isPerfectSquare(int temp) {
        int s = (int) Math.sqrt(temp);
        return (s * s == temp);
    }

    public static boolean isFibonacci(int num) {
        return isPerfectSquare(5 * num * num + 4) || isPerfectSquare(5 * num * num - 4);
    }
```
