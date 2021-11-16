---
title : "Hash Algorithm - Uniformity"
date : "2021-11-16"
tags : [CodeStudy,HashAlgorithm,uniformity]
topics : [CodeStudy]
---

## Definition
one of properties for Hash algorithm 
map the expected inputs as evenly as possible over its output range without hash crash. 


## Example
[input]->[output]
#### first hash algorithm
A->03
B->02
C->03
#### second hash algorithm
A->01
B->02
C->03

#### explanation
if the uniformity of hash algorithm is high, it less create hash crush.
Thus, the second hash algorithm's uniformity is higher than the first hash algorithm

## conclusion
- high uniformity = less hash crush = higher possible to learn with O(1) of time complexity

## other questions

#### Can we possible to make perfect hash algorithm that does not make any hash crush?
It is possible, but, it need to limit range a lot. Too little to use for out usual purpose such as Big data.

#### find uniformity
used chi-squared test
expected mapping / actual mapping

$$\frac{\sum_{j=0}^{m-1}  \left ( b_{j} \right ) \left ( b_j+1 \right )/2}{\left ( n/2m \right )\left ( n+2m-1 \right )}$$

n=number of keys
m=number of buckets
b(j)=items in buckets

Result should be in range 0.95~1.05.