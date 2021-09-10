---
title : "Selection Sort"
date : "2021-09-10"
tags : [CodeStudy,SelectionSort]
topics : [CodeStudy]
---
## Definition

one of sort algorithms

## Technique

Brute Force

### Algorithm steps

1. find smallest number in the list
2. swap the smallest number and first place
3. the first element is sorted
4. find smallest number in the list except the sorted element.
5. swap the smallest number and second place
5. Repeat 1~5 until all of them sorted.
### Example-Java

```java

    public static int[] selectionSort(int[] input) {
        for (int i = 0; i < input.length - 1; ++i) {
            for (int j = input.length - 1; j > i; --j) {
                if (input[j] < input[i]) {
                    int temp = input[i];
                    input[i] = input[j];
                    input[j] = temp;
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
