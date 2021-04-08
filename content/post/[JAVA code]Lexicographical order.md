---
title : "[JAVA code]Lexicographical order"
date : "2021-04-04"
tags : [Java Dictionary,Lexicographical order, Dictionary order, lexicographic, lexical order,alphabetical order]
topics : [Java]
---

- Time complexity : $O(n\ log\ n)$
- Space complexity : $O(1)$

```java

    Collections.sort(List<String>_values);
```
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