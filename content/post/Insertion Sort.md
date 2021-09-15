---
title : "Insertion Sort"
date : "2021-09-15"
tags : [CodeStudy,InsertionSort]
topics : [CodeStudy]
---

## Definition

one of sort algorithms

## Technique

Brute Force

### Algorithm steps

1. first loop first to the end
2. compare looping number and left side.
3. if left side number is bigger than right side, swap them.
4. since number swapped, check left side numbers and make sure the left side is getting smaller
5. step 4 means that if left side is small and does not swap, it does not need to check further.
6. Repeat 1~5 until all of them sorted.

### Example-Java

```java

    public static int[] insertSort(int[] input) {
        for (int i = 1; i < input.length; ++i) {
            int chkPos = i;
            while (chkPos > 0) {
                if (input[chkPos - 1] > input[chkPos]) {
                    int temp = input[chkPos];
                    input[chkPos] = input[chkPos - 1];
                    input[chkPos - 1] = temp;
                }
                --chkPos;
            }
        }
        return input;
    }
```

### Avg. time complexity

$O(n^2)$

### Worst time complexity

$O(n^2)$ 

### space complexity

$O(1)$ 

### stability

no

---

## How to calculate

### numbers of loop
$n-1$

### The most visited place of the list
$n-1$ (the last place)

### The least visited place of the list

$1$ (the first place)

### Avg. visited numbers of the list

(The most visited place of the list+The least visited place of the list)/2 $= \frac{(n-1+1)}{2} = \frac{n}{2}$

### Polynomial Time

numbers of loop\*Avg. visited numbers of the list $=(n-1)\cdot \frac{n}{2}$

### Time Complexity

$$O(Polynomial\; Time)=O((n-1)\cdot \frac{n}{2})=O((\frac{n^2}{2}-\frac{n}{2}))=O(n^2)$$