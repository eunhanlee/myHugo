---
title : "Reverse Integer"
date : "2021-04-21"
tags : [algorithm problem solving, Reverse Integer]
topics : [ProblemSolving]
---
## Problem

[Problem_Link](https://leetcode.com/problems/reverse-integer/){: .btn .btn-green}

- 1 hour limit
- no search on internet
  

Given a signed 32-bit integer `x`, return `x` *with its digits reversed*. If reversing `x` causes the value to go outside the signed 32-bit integer range `[-231, 231 - 1]`, then return `0`.

**Assume the environment does not allow you to store 64-bit integers (signed or unsigned).**

**Example 1:**

```
Input: x = 123
Output: 321
```

**Example 2:**

```
Input: x = -123
Output: -321
```

**Example 3:**

```
Input: x = 120
Output: 21
```

**Example 4:**

```
Input: x = 0
Output: 0
```

**Constraints:**

- `231 <= x <= 231 - 1`

## My Answer

### My code

```java
class Solution {
    public int reverse(int x) {
        int rev = 0;
        while (x != 0) {
            int pop = x % 10;
            x /= 10;
            if (rev > Integer.MAX_VALUE / 10 || (rev == Integer.MAX_VALUE / 10 && pop > (Integer.MAX_VALUE % 10)))
                return 0;
            if (rev < Integer.MIN_VALUE / 10 || (rev == Integer.MIN_VALUE / 10 && pop < (Integer.MIN_VALUE % 10)))
                return 0;

            rev = rev * 10 + pop;
        }
        return rev;
    }
}
```

### My result

Runtime: 1 ms, faster than 100.00% of Java online submissions for Reverse Integer.
Memory Usage: 38.2 MB, less than 8.59% of Java online submissions for Reverse Integer.

## Reflect on

- This time I skipped overview and it caused issue. I did not notice the edge case that should return 0 when there is overflow.
- instead of detecting with overflow in 32 bits, compare the result to verify overflowed or not is brilliant. I knew that overflow do not cause error but did not think that way.

## Other Answers

- My accepted 15 lines of code for Java

  ```
  public int reverse(int x)
  {
      int result = 0;

      while (x != 0)
      {
          int tail = x % 10;
          int newResult = result * 10 + tail;
          if ((newResult - tail) / 10 != result)
          { return 0; }
          result = newResult;
          x = x / 10;
      }

      return result;
  }
  ```

## Additional Study needed
