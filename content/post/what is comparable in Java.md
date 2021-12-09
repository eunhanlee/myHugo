---
title : "what is comparable in Java"
date : "2021-12-09"
tags : [CodeStudy, comparable, Java, WhatIs,]
topics : [CodeStudy]
---

### Hierarchy

package: java.lang.Comparable

### Definition

Sorting interface that designed for **a condition** by overriding **compareTo** method. For example, you can sort list in ascending order of size.

### about the compareTo() method

if compareTo() method return positive number, swap the input parameters  
else will be remain same

| condition                           | return   |
| ----------------------------------- | -------- |
| First parameter < second parameter  | negative |
| First parameter == second parameter | 0        |
| First parameter > second parameter  | positive |

### How to use

customObject implements Comparable<>

Arrays.sort(customObject);  
Collections.sort(customObject);

### Example

```java

import java.lang.Comparable;

public class customPoint implements Comparable<customPoint> {

    private int x = 0;
    private int y = 0;

    public customPoint(int x, int y) {
        this.x = x;
        this.y = y;

    }

    public int getX() {
        return x;
    }

    public int getY() {
        return y;
    }

    @Override
    public int compareTo(customPoint p2) {
        if (this.y > p2.y) {
            return 1; // y is in ascending order
        }
        return -1;
    }
}
```

```java

import java.util.List;
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {

        List<customPoint> pointList2 = new ArrayList<>();
        pointList2.add(new customPoint(10, 10));
        pointList2.add(new customPoint(1, 8));
        pointList2.add(new customPoint(5, 2));
        pointList2.add(new customPoint(1, 2));
        pointList2.add(new customPoint(5, 5));
        pointList2.add(new customPoint(10, 1));

        System.out.println("current list");
        for (customPoint temp : pointList2) {
            System.out.println("x: " + temp.getX() + "  " + "y: " + temp.getY());
        }

        System.out.println("sorted list");

        Collections.sort(pointList2);

        for (customPoint temp : pointList2) {
            System.out.println("x: " + temp.getX() + "  " + "y: " + temp.getY());
        }

    }

}
```

### Result

```
current list
x: 10  y: 10
x: 1  y: 8
x: 5  y: 2
x: 1  y: 2
x: 5  y: 5
x: 10  y: 1
sorted list
x: 10  y: 1
x: 1  y: 2
x: 5  y: 2
x: 5  y: 5
x: 1  y: 8
x: 10  y: 10
```
