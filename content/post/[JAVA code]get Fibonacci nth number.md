---
title : "[JAVA code]get Fibonacci nth number"
date : "2021-04-12"
tags : [Java Dictionary,Fibonacci nth number,Fibonacci,Fibonacci number]
topics : [Java]
---

### math

```java
public int fib(int N) {
        double goldenRatio = (1 + Math.sqrt(5)) / 2;
        return (int)Math.round(Math.pow(goldenRatio, N)/ Math.sqrt(5));
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


