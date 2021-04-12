---
title : "[JAVA code]switch"
date : "2021-04-12"
tags : [Java Dictionary,switch,switch statement]
topics : [Java]
---

```java

    public static int getNum(char s) {
        return switch (s) {
            case 'I' -> 1;
            case 'V' -> 5;
            case 'X' -> 10;
            case 'L' -> 50;
            case 'C' -> 100;
            case 'D' -> 500;
            case 'M' -> 1000;
            default -> 0;
        };
    }
```