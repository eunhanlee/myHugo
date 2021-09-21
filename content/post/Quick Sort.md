---
title : "Quick Sort"
date : "2021-09-21"
tags : [CodeStudy,QuickSort]
topics : [CodeStudy]
---

## Definition

one of sort algorithms

- The most important sort algorithm
- Use this algorithm anywhere with any languages
- The best way to avoid worst time complexity is pick pivot randomly.
- if program most not have $O(n^2)$, need to use other sorting algorithm.

## Technique
Decrease and Conquer 

### Algorithm steps
Recusively loop based on Lomuto.

1. pick pivot the most right element.
2. left side will be smaller than pivot value and right side will be bigger than pivot.
3. let's say most left value is selected index and comaparing index without pivot.
4. if comaparing index value is smaller than pivot, swap with selected index and increase the selected index.
5. if comaparing index value is bigger than or equal pivot, increase the comaparing index.
6. when the comaparing index is equal to pivot index, swap pivot and the selected index.
7. Recusively loop step 1~6.

#### how to pick pivot
1. Lomuto
   - pivot : the most right element.
   - starting selected index (i) : 0
   - starting comaparing index (j) : 0

2. Hoare
   - pivot : the most left element.
   - starting selected index (i) : 1
   - starting comaparing index (j) : the most right element.

3. Randomly Choose

## Java code - Lomuto

```java

   public static void quickSort(int[] input) {
        quickSortRecur(input, 0, input.length - 1);
    }


    public static void quickSortRecur(int[] input, int left, int right) {

        if (left >= right) {
            return;
        }

        int pivotPos = partition(input, left, right);

        quickSortRecur(input, left, pivotPos - 1);
        quickSortRecur(input, pivotPos + 1, right);

    }

    public static void swap(int[] input, int a, int b) {
        int temp = input[a];
        input[a] = input[b];
        input[b] = temp;

    }

    public static int partition(int[] input, int left, int right) {
        int pivot = input[right];

        int i = (left - 1);
        for (int j = left; j < right; ++j) {
            if (input[j] < pivot) {
                ++i;
                swap(input, i, j);
            }
        }
        swap(input, (i + 1), right);
        return i + 1;
    }
```
## Java code - Hoare
```java
 public static void quickSort(int[] input) {
        quickSortRecur(input, 0, input.length - 1);
    }

    public static void quickSortRecur(int[] input, int left, int right) {

        if (left >= right) {
            return;
        }

        int pivotPos = partition(input, left, right);

        quickSortRecur(input, left, pivotPos);
        quickSortRecur(input, pivotPos + 1, right);

    }

    public static void swap(int[] input, int a, int b) {
        if (a != b) {
            int temp = input[a];
            input[a] = input[b];
            input[b] = temp;
        }

    }

    public static int partition(int[] input, int left, int right) {
        int pivot = input[left];
        int i = left - 1;
        int j = right + 1;

        while (true) {
            do {
                ++i;
            } while (input[i] < pivot);

            do {
                --j;
            } while (input[j] > pivot);

            if (i >= j) {
                return j;
            }

            swap(input, i, j);
        }
    }
```

#### Avg. time complexity 
$O(n\, log\, n)$ 
#### Worst time complexity
$O(n^2)$  
#### space complexity
$O(log\, n)$
#### stability 
no

## How to calculate
### numbers of loop
- base recursion: $O(n)$
- If separated evenly : $O(log\,n)$
- If separated not evenly : $O(n)$

#### Time Complexity
- If separated evenly : $  O(n \cdot log\,n)=O(n\,log\,n)$
- If separated not evenly (the worst case) : $O(n  \cdot n)=O(n^2)$


