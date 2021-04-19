---
title : "Reorder Data in Log Files"
date : "2021-04-19"
tags : [algorithm problem solving, Reorder Data in Log Files]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/reorder-data-in-log-files/)

- 1 hour limit
- no search on internet
 

You have an array of `logs`.  Each log is a space delimited string of words.

For each log, the first word in each log is an alphanumeric *identifier*.  Then, either:

- Each word after the identifier will consist only of lowercase letters, or;
- Each word after the identifier will consist only of digits.

We will call these two varieties of logs *letter-logs* and *digit-logs*.  It is guaranteed that each log has at least one word after its identifier.

Reorder the logs so that all of the letter-logs come before any digit-log.  The letter-logs are ordered lexicographically ignoring identifier, with the identifier used in case of ties.  The digit-logs should be put in their original order.

Return the final order of the logs.

**Example 1:**

```
Input: logs = ["dig1 8 1 5 1","let1 art can","dig2 3 6","let2 own kit dig","let3 art zero"]
Output: ["let1 art can","let3 art zero","let2 own kit dig","dig1 8 1 5 1","dig2 3 6"]

```

**Constraints:**

1. `0 <= logs.length <= 100`
2. `3 <= logs[i].length <= 100`
3. `logs[i]` is guaranteed to have an identifier, and a word after the identifier.

## My Answer

### My code

```java
class Solution {
    public String[] reorderLogFiles(String[] logs) {

        sort(logs, 0, logs.length - 1);

        return logs;
    }

    void merge(String arr[], int l, int m, int r) {
        // Find sizes of two subarrays to be merged
        int n1 = m - l + 1;
        int n2 = r - m;

        /* Create temp arrays */
        String L[] = new String[n1];
        String R[] = new String[n2];

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
            String lstr = L[i].substring(4).replaceAll("\\s+|[0-9]+", "");
            String rstr = R[j].substring(4).replaceAll("\\s+|[0-9]+", "");

            System.out.println(lstr);
            System.out.println(rstr);

            System.out.println("=======");

            int g = 0;

//            while (lstr.charAt(g) == rstr.charAt(g)) {
//                g++;
//                if (g >= lstr.length() || g >= rstr.length()) {
//                    g = 0;
//                    break;
//                }
//
//            }
            int lnum = 0;
            int rnum = 0;
            if (0 == lstr.length() || 0 == rstr.length()){
                 lnum = 0;
                 rnum = 0;
            }else{
                 lnum = lstr.charAt(g) - 'a';
                 rnum = rstr.charAt(g) - 'a';
            }



            if (rnum >= lnum) {
                arr[k] = L[i];
                i++;
            } else {
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
    void sort(String arr[], int l, int r) {
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
}
```

### My result

fail

## Reflect on

- I created merge sort to reorder but the orde condition is 3. It is too complicated and not working. It will work that merge sort 3 times for each condition
- The conditions are

  1. ignore alphanumeric identifier
  2. letter-logs are ordered lexicographically
  3. digit-logs should be put in their original order

  "let1 art can 2 4 6"

  let1 = ignored

  art can = lexicographically

  2 4 6 = original order

- wasted too much time with merge sorting which is not important.. sould've use

## Additional Study needed

- Comparator
- sort is stable and unstable
