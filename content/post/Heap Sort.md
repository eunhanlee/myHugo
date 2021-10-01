---
title : "Heap Sort"
date : "2021-10-01"
tags : [CodeStudy,HeapSort]
topics : [CodeStudy]
---

## Definition
- one of sort array
- data structure based on binary tree
- insert data into binary tree and print out from the tree


### Algorithm steps
1. insert data into binary tree 
2. The data sorted as binary tree
3. print

## Java code
```java

    public static void heapSort(int arr[]) {
        int n = arr.length;

        // Build heap (rearrange array)
        for (int i = n / 2 - 1; i >= 0; i--)
            heapTree(arr, n, i);

        // One by one extract an element from heap
        for (int i = n - 1; i > 0; i--) {
            // Move current root to end
            int temp = arr[0];
            arr[0] = arr[i];
            arr[i] = temp;

            // call max heapify on the reduced heap
            heapTree(arr, i, 0);
        }
    }

    // To heapify a subtree rooted with node i which is
    // an index in arr[]. n is size of heap
    public static void heapTree(int arr[], int n, int i) {
        int largest = i; // Initialize largest as root
        int l = 2 * i + 1; // left = 2*i + 1
        int r = 2 * i + 2; // right = 2*i + 2

        // If left child is larger than root
        if (l < n && arr[l] > arr[largest])
            largest = l;

        // If right child is larger than largest so far
        if (r < n && arr[r] > arr[largest])
            largest = r;

        // If largest is not root
        if (largest != i) {
            int swap = arr[i];
            arr[i] = arr[largest];
            arr[largest] = swap;

            // Recursively heapify the affected sub-tree
            heapTree(arr, n, largest);
        }
    }
```
*this code is from https://www.geeksforgeeks.org/heap-sort/

#### Avg. time complexity 
$O(n\, log\, n)$
#### Worst time complexity
$O(n\, log\, n)$
#### space complexity
$O(1)$
#### stability 
no

## How to calculate
### numbers of loop
- insert to binary tree : $O(log\, n)$
- visit every node to print : $O(n)$

#### Time Complexity
$O(n) \cdot O(log\, n)=O(n\, log\, n)$