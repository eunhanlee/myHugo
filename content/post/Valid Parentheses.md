---
title : "Valid Parentheses"
date : "2021-04-16"
tags : [algorithm problem solving, Valid Parentheses]
topics : [ProblemSolving]
---

## Problem

- 1 hour limit
- no search on internet

[Problem_Link](https://leetcode.com/problems/valid-parentheses/)

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

**Example 1:**

```
Input: s = "()"
Output: true

```

**Example 2:**

```
Input: s = "()[]{}"
Output: true

```

**Example 3:**

```
Input: s = "(]"
Output: false

```

**Example 4:**

```
Input: s = "([)]"
Output: false

```

**Example 5:**

```
Input: s = "{[]}"
Output: true

```

**Constraints:**

- `1 <= s.length <= 104`
- `s` consists of parentheses only `'()[]{}'`.

## My Answer

### My code

```java
class Solution {
    public boolean isValid(String s) {
        HashMap<Character, Character> map = new HashMap<>(3);
        map.put('(', ')');
        map.put('[', ']');
        map.put('{', '}');

        Stack<Character> stack = new Stack<>();

        if(s.length()<2)
            return false;

        for (int i = 0; i < s.length(); i++) {
            if (map.containsKey(s.charAt(i))) {
                stack.push(map.get(s.charAt(i)));
            } else {
                if(stack.isEmpty()){
                    return false;
                }
                if (!stack.pop().equals(s.charAt(i)))
                    return false;
            }

        }


        return stack.isEmpty();


    }
}
```

## Reflect on

- wrong approach. the algorithm itself was too slow. better way is using stack and same results and compare
- need to think one more step

## Additional Study needed
