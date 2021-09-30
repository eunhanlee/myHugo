---
title : "Merge Sort"
date : "2021-09-30"
tags : [CodeStudy,MergeSort]
topics : [CodeStudy]
---

## Definition

one of sort algorithms

## Technique
Decrease and Conquer 

### Algorithm steps
Recusively loop
1. Recusively loop left side and right side until the input array cannot separated
2. every separated parts only one element is in there. This is sorted.
3. merge arrays with sort.

## Java code

```java

   public static void mergeSort(int[] input) {
        mergeSortRecurr(input, 0, input.length - 1);
    }

    public static void mergeSortRecurr(int[] input, int left, int right) {
        if (left < right) {
            int midPos = left + (right - left) / 2;

            mergeSortRecurr(input, left, midPos);
            mergeSortRecurr(input, midPos + 1, right);
            merge(input, left, right, midPos);
        }
    }

    public static void merge(int[] input, int left, int right, int midPos) {
        //mid pos does not check unlike the left and right
        int temp1 = midPos - left + 1;
        int temp2 = right - midPos;

        //temp array and copy
        int[] L = new int[temp1];
        int[] R = new int[temp2];
        for (int i = 0; i < temp1; ++i)
            L[i] = input[left + i];
        for (int j = 0; j < temp2; ++j)
            R[j] = input[midPos + 1 + j];


        int i = 0;
        int j = 0;
        int k = left;

        while (i < temp1 && j < temp2) {
            if (L[i] <= R[j]) {
                input[k] = L[i];
                ++i;
            } else {
                input[k] = R[j];
                ++j;
            }
            ++k;
        }

        while (i < temp1) {
            input[k] = L[i];
            ++i;
            ++k;
        }

        while (j < temp2) {
            input[k] = R[j];
            ++j;
            ++k;
        }
    }
```
#### Avg. time complexity 
$O(n\, log\, n)$
#### Worst time complexity
$O(n\, log\, n)$
#### space complexity
$O(n)$
#### stability 
yes

## How to calculate
### numbers of loop
- base recursion for merge: $O(n)$
- separated evenly : $O(log\,n)$

#### Time Complexity
$O(n) \cdot O(log\, n)=O(n\, log\, n)$

