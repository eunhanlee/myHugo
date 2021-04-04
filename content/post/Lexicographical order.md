---
title : Lexicographical order
date : 2021-04-04
tags : [code knowledge, Lexicographical order, Dictionary order, lexicographic, lexical order,alphabetical order]
topics : [CodeKnowledge]
katex: true
markup: "mmark"
---
## Definition
Dictionary order

According to ASCII rules
[numbers][capital letters][lowercase letters]
0 ~ 9, A ~ Z, a ~ z



## Example
```java
public static void main(String[] args) {
    List<String> values = Arrays.asList("A", "a", "B", "b", "1", "2");
    Collections.sort(values);
}
```
1,2,A,B,a,b
```java
 public static void main(String[] args) {
      String[] words = { "Peach", "Orange", "Mango", "Cherry", "Apple" };
      int n = 5
      for(int i = 0; i < n-1; ++i) {
         for (int j = i + 1; j < n; ++j) {
            if (words[i].compareTo(words[j]) > 0) {
               String temp = words[i];
               words[i] = words[j];
               words[j] = temp;
            }
         }
      }
   }
```
Apple,Cherry,Mango,Orange,Peach

## Explaination
Since the 'cmpareTo' method compare strings with ascii code, it will
the value 0 if the argument string is equal to this string; 
a value less than 0 if this string is lexicographically less than the string argument; 
a value greater than 0 if this string is lexicographically greater than the string argument.

For example, a.compareTo(b) will return -1 because a = 97 and b=98 in ascii code.
Then, 97-98= -1. 