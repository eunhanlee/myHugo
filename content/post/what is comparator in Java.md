---
title : "what is comparator in Java"
date : "2021-12-09"
tags : [CodeStudy, comparator , Java, WhatIs]
topics : [CodeStudy]
---

### Hierarchy

package: java.util.Comparator

### Definition

Sorting interface that designed for **mutiple special conditions** by creating **compare** method. For example, you can sort list in ascending order of size and descending order of letters.

### about the compare() method

if compare() method return positive number, swap the input parameters  
else will be remain same

| condition                           | return   |
| ----------------------------------- | -------- |
| First parameter < second parameter  | negative |
| First parameter == second parameter | 0        |
| First parameter > second parameter  | positive |

### How to use

MyComparator implements Comparator<>

MyComparator myComparator = new MyComparator();  
Arrays.sort(array, myComparator);  
Collections.sort(list, myComparator);

### Example

```java
import java.awt.*;
import java.util.Comparator;

public class MyComparator implements Comparator<Point> {

    public int compare(Point p1, Point p2) {
        if (p1.x > p2.x) {
            return 1; // x is in ascending order
        } else if (p1.x == p2.x) {
            if (p1.y < p2.y) { // y is in descending order
                return 1;
            }
        }
        return -1;
    }
}
```

```java
import java.awt.*;
import java.util.List;
import java.util.ArrayList;
import java.util.Collections;


public class Main {
    public static void main(String[] args) {

        List<Point> pointList = new ArrayList<>();
        pointList.add(new Point(10, 10));
        pointList.add(new Point(1, 8));
        pointList.add(new Point(5, 2));
        pointList.add(new Point(1, 2));
        pointList.add(new Point(5, 5));
        pointList.add(new Point(10, 1));

        System.out.println("current list");
        for (Point temp : pointList) {
            System.out.println("x: " + temp.x + "  " + "y: " + temp.y);
        }

        MyComparator myComparator = new MyComparator();
        Collections.sort(pointList, myComparator);

        System.out.println("sorted list");
        for (Point temp : pointList) {
            System.out.println("x: " + temp.x + "  " + "y: " + temp.y);
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
x: 1  y: 8
x: 1  y: 2
x: 5  y: 5
x: 5  y: 2
x: 10  y: 10
x: 10  y: 1
```
