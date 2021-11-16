---
title : "Hash Algorithm - Hash Crash"
date : "2021-11-16"
tags : [CodeStudy,HashAlgorithm,HashCrash]
topics : [CodeStudy]
---

## Definition

one of problems while using the hash algorithm.
If the input value is different, the output value should be different. But, the output is same.
We calls, "Hash Crash"

## Characteristics

- less hash crush is better hash algorithm
- No hash crush is almost impossible.

## Example

[input]->[output]

A->03
B->02
C->03

The output of A and C are same. This is hash crush.

## solution

Most hash algorithm search next output when hash crush happen.
For example, the out put of C is 03, thus hash algorithm check 04 and return 04 because the output is not in use.
