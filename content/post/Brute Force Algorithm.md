---
title : "Brute Force Algorithm"
date : "2021-09-08"
tags : [CodeStudy,BruteForceAlgorithm]
topics : [CodeStudy]
---
### Definition

check every possible way to find answer.

### Points

- No efficiency
- most intuitive way to solving problems
- increase exponential growth
- one of exhaustive search

### Example

If you find password with brute force algorithm,
n=password digits, let's assume 4
k=each digit can contain numbers, let's assume 0~9
Then, all possible ways are $k^n=10^4=10000$
The combination can be in 10000 ways.

When the passwords digits are more than 4, it will be exponential growth.
Thus, longer password is better.