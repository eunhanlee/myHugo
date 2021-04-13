---
title : "Verifying an Alien Dictionary"
date : "2021-04-13"
tags : [algorithm problem solving, Verifying an Alien Dictionary]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/verifying-an-alien-dictionary/)


- 1 hour limit
- no search on internet


In an alien language, surprisingly they also use english lowercase letters, but possibly in a different `order`. The `order` of the alphabet is some permutation of lowercase letters.

Given a sequence of `words` written in the alien language, and the `order` of the alphabet, return `true` if and only if the given `words` are sorted lexicographicaly in this alien language.

**Example 1:**

```
Input: words = ["hello","leetcode"], order = "hlabcdefgijkmnopqrstuvwxyz"
Output: true
Explanation: As 'h' comes before 'l' in this language, then the sequence is sorted.

```

**Example 2:**

```
Input: words = ["word","world","row"], order = "worldabcefghijkmnpqstuvxyz"
Output: false
Explanation: As 'd' comes after 'l' in this language, then words[0] > words[1], hence the sequence is unsorted.

```

**Example 3:**

```
Input: words = ["apple","app"], order = "abcdefghijklmnopqrstuvwxyz"
Output: false
Explanation: The first three characters "app" match, and the second string is shorter (in size.) According to lexicographical rules "apple" > "app", because 'l' > '∅', where '∅' is defined as the blank character which is less than any other character (More info).

```

**Constraints:**

- `1 <= words.length <= 100`
- `1 <= words[i].length <= 20`
- `order.length == 26`
- All characters in `words[i]` and `order` are English lowercase letters.

## My Answer

### My code

```java
class Solution {
    public boolean isAlienSorted(String[] words, String order) {
        HashMap<Character, Integer> map = new HashMap<>();
        map.put(' ', 0);
        for (int i = 0; i < order.length(); i++) {
            map.put(order.charAt(i), i + 1);
        }

        for (int i = 1; i < words.length; i++) {
            char prev = words[i - 1].charAt(0);
            words[i - 1] = words[i - 1].substring(1);
            char curr = words[i].charAt(0);
            words[i] = words[i].substring(1);


            while (prev == curr) {
                if (words[i - 1].length() == 0 ){
                    prev=' ';
                    break;
                }
                if (words[i].length() == 0){
                    curr=' ';
                    break;
                }

                prev = words[i - 1].charAt(0);
                curr = words[i].charAt(0);
                words[i - 1] = words[i - 1].substring(1);
                words[i] = words[i].substring(1);

            }

            if (map.get(curr) < map.get(prev)) {
                return false;
            }


        }

        return true;
    }

}
```

## Reflect on

- I did not know what lexicographicaly mean
- Never see the `continue search`. It seems good for time complexity
- basic algorithm is same. But understanding of data types made slow such as calulating with char type
- I tend to use more memory space such as more variables. Need to care.

## Additional Study needed

- lexicographical order
- +-\*/ with string and char type.
