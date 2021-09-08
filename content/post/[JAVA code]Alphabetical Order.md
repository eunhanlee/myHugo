---
title : "[JAVA code]Alphabetical Order"
date : "2021-04-04"
tags : [CodeDictionary,LexicographicalOrder,DictionaryOrder,AlphabeticalOrder]
topics : [CodeDictionary]
---

## Alphabetical Order

According to ASCII rules
[numbers][capital letters][lowercase letters]
0 ~ 9, A ~ Z, a ~ z

- Time complexity : $O(n\ log\ n)$
- Space complexity : $O(1)$
### For List
```java

    Collections.sort(List<String>_values);
```
### For Array
```java

    Arrays.sort(String[]array);
```

---

- Time complexity : $O(n^2)$
- Space complexity : $O(1)$

```java

    public static String[] LexicalOrder(String[] words) {
        int n = words.length;
        for (int i = 0; i < n - 1; ++i) {
            for (int j = i + 1; j < n; ++j) {
                if (words[i].compareTo(words[j]) > 0) {
                    String temp = words[i];
                    words[i] = words[j];
                    words[j] = temp;
                }
            }
        }
        return words;
    }
```