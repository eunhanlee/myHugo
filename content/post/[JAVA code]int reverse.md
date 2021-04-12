---
title : "[JAVA code]int reverse"
date : "2021-04-12"
tags : [Java Dictionary,Reverse,Int reverse]
topics : [Java]
---

## int reverse without using string

- Time complexity : $O(n)$
- Space complexity : $O(1)$

```java

    public static int reverseInt(int input) {
        int output = 0;
        int length = ((int) (Math.log10(input)) + 1);

        for (int i = 0; i < length; ++i) {
            output = output * 10 + input % 10;
            input = input / 10;
        }

        return output;
    }
```
---