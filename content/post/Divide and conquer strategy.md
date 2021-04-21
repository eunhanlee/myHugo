---
title : "Divide and conquer strategy"
date : "2021-04-21"
tags : [code knowledge, Divide and Conquer]
topics : [CodeKnowledge]
---

## Purpose

split problem into sub problems as much as possible and merge all of them to answer

### Divide and conquer algorithms vs. Dynamic programming?

Divide and conquer algorithms does not use subproblems' results for other sub problems.

But, dynamic programming uses other resoults of subproblem. 

### Usually use in..

- quick sort
- merge sort
- binary sort
- Fast Fourier Transform (FFT)
- big data analysis

## Explanation

1. divide: separate problems that are smaller instances of the same problem
2. conquer: solve the subprolems recursively
3. merge: add all of subanswers to find answer

## Example

### merge sort

#### step 1. check data size and if 0 or 1, it is sorted

![](https://raw.githubusercontent.com/eunhanlee/img/main/0006.png)

#### step 2. separate into half repeatly


 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0007.png)


#### step 3. merge separated units by order

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0008.png)


#### step 4. repeat step 3 untill the data set become one

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0009.png)


#### code

    ```java
    class MergeSort 
    {
        // Merges two subarrays of arr[].
        // First subarray is arr[l..m]
        // Second subarray is arr[m+1..r]
        void merge(int arr[], int l, int m, int r)
        {
            // Find sizes of two subarrays to be merged
            int n1 = m - l + 1;
            int n2 = r - m;
     
            /* Create temp arrays */
            int L[] = new int[n1];
            int R[] = new int[n2];
     
            /*Copy data to temp arrays*/
            for (int i = 0; i < n1; ++i)
                L[i] = arr[l + i];
            for (int j = 0; j < n2; ++j)
                R[j] = arr[m + 1 + j];
     
            /* Merge the temp arrays */
     
            // Initial indexes of first and second subarrays
            int i = 0, j = 0;
     
            // Initial index of merged subarry array
            int k = l;
            while (i < n1 && j < n2) {
                if (L[i] <= R[j]) {
                    arr[k] = L[i];
                    i++;
                }
                else {
                    arr[k] = R[j];
                    j++;
                }
                k++;
            }
     
            /* Copy remaining elements of L[] if any */
            while (i < n1) {
                arr[k] = L[i];
                i++;
                k++;
            }
     
            /* Copy remaining elements of R[] if any */
            while (j < n2) {
                arr[k] = R[j];
                j++;
                k++;
            }
        }
     
        // Main function that sorts arr[l..r] using
        // merge()
        void sort(int arr[], int l, int r)
        {
            if (l < r) {
                // Find the middle point
                int m = (l + r) / 2;
     
                // Sort first and second halves
                sort(arr, l, m);
                sort(arr, m + 1, r);
     
                // Merge the sorted halves
                merge(arr, l, m, r);
            }
        }
     
        /* A utility function to print array of size n */
        static void printArray(int arr[])
        {
            int n = arr.length;
            for (int i = 0; i < n; ++i)
                System.out.print(arr[i] + " ");
            System.out.println();
        }
     
        // Driver code
        public static void main(String args[])
        {
            int arr[] = { 12, 11, 13, 5, 6, 7 };
     
            System.out.println("Given Array");
            printArray(arr);
     
            MergeSort ob = new MergeSort();
            ob.sort(arr, 0, arr.length - 1);
     
            System.out.println("\nSorted array");
            printArray(arr);
        }
    }
    /* This code is contributed by Rajat Mishra */
    ```
[Source code From geeksforgeeks](https://www.geeksforgeeks.org/java-program-for-merge-sort/)

### Complexity Analysis of merge sort

- Time complexity : $O(n\ log\ n)$
- Space complexity : $O(n)$