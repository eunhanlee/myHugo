---
title : "Bubble Sort"
date : "2021-09-09"
tags : [CodeStudy,BubbleSort]
topics : [CodeStudy]
---

## Definition

one of sort algorithms

## Technique

Brute Force

### Algorithm steps

1. compare two numbers
2. smaller number will be left and bigger number will be in right side.
3. compare over and over again untill the end of the list
4. Now, biggest number will stay in most right side. This number is sorted
5. Start over from first number except sorted place.
6. Repeat 1~5 until all of them sorted.

### Example-Java

```java

    public static int[] bubbleSort(int[] input) {
        for (int i = 0; i < input.length - 1; ++i) {
            for (int j = 0; j < input.length - i - 1; ++j) {
                if (input[j] > input[j + 1]) {
                    int temp = input[j];
                    input[j] = input[j + 1];
                    input[j + 1] = temp;
                }
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

yes

---

## How to calculate

### numbers of loop

$n-1$

### The most visited place of the list

$n-1$ (the first place)

### The least visited place of the list

$1$ (the last place)

### Avg. visited numbers of the list

(The most visited place of the list+The least visited place of the list)/2 $= \frac{(n-1+1)}{2} = \frac{n}{2}$

### Polynomial Time

numbers of loop\*Avg. visited numbers of the list $=(n-1)\cdot \frac{n}{2}$

### Time Complexity

$$O(Polynomial\; Time)=O((n-1)\cdot \frac{n}{2})=O((\frac{n^2}{2}-\frac{n}{2}))=O(n^2)$$
