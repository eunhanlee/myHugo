---
title : "what is diffence between comparator and compatable in JAVA"
date : "2021-04-08"
tags : [coding questions, diffence between comparator and compatable, comparator , compatable , Java]
topics : [CodingQuestions]
---


| Comparable                                          | Comparator                                         |
| --------------------------------------------------- | -------------------------------------------------- |
| java.lang package.                                  | java.util package.                                 |
| Sorting interface that designed for **a condition** | interface that designed for **mutiple conditions** |
| Comparable **affects** the original class           | Comparator **doesn't affect** the original class   |
| compareTo() method with 1 parameter                 | compare() method with 2 parameters                 |
| Collections.sort(List)                              | Collections.sort(List, Comparator)                 |
| Arrays.sort(array)                                  | Arrays.sort(array, myComparator);                  |

## Definition

Both interfaces are very similer because they are for sorting lists and arrays. However, one is for one condition and other one is for mutiple conditions.

[Comparable ](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Comparable.html)

- Comparable is for one condition and override the compareTo method.
- It can sort with mutiple conditions, but that will affects the original class.
- it defines sort condition for object. It built in to the object. (Collections.sort(List))
- For example, if you sort your object by mutiple conditions with compatable, you cannot sort simple ascending order because overrided the comareTo method.

[Comparator ](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/Comparator.html)

- Comparator is for mutiple conditions and create compare method.
- It can sort with mutiple conditions, but that will not affects the original class.
- it defines conditions and put conditions when sort. (Collections.sort(List, Comparator))
- For example, if you sort your object by mutiple conditions with comparator, you still can sort simple ascending order with Collections.sort.

## Conclusion

It is possible to put mutiple conditions into the comparable. However, that may cause some confustion because it will override the compareTo() method. To computer, it does not matter. But we, computer programmers, should care about it. Thus, you should use the comparable for one condition and comparator for multiple conditions.

## Example

### custom class with compatable

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
    public int compareTo(customPoint p2) { // this is possible. mutiple condition. But bad idea.
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

### comparator

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

### main

```java

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
        System.out.println("sorted list");
        MyComparator myComparator = new MyComparator();
        Collections.sort(pointList, myComparator);
        for (Point temp : pointList) {
            System.out.println("x: " + temp.x + "  " + "y: " + temp.y);
        }
        System.out.println("===========================================================");

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
