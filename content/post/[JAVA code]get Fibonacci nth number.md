---
title : "[JAVA code]get Fibonacci nth number"
date : "2021-04-12"
tags : [Java Dictionary,Fibonacci nth number,Fibonacci,Fibonacci number]
topics : [Java]
---

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
        if (num <= 1) return num;
        return fibRecursive(num - 2) + fibRecursive(num - 1);
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


