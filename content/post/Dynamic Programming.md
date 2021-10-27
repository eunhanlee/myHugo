---
title : Dynamic Programming
date : 2021-04-01
tags : [CodeStudy, DynamicProgramming]
topics : [CodeStudy]
---

## Definition

algorithmic problem solving technique that split into many simple subproblems and reduce steps of subproblems. In other wards, separates into subproblems and get solution by addition of all subproblems.

## Example

if you calculate $2^1+2^2+2^3+2^4+2^5$ and display each numbers,

$2^1=2=2$

$2^2=2*2=2^1*2$

$2^3=2*2*2=2^2*2$

$2^4=2*2*2*2=2^3*2$

$2^5=2*2*2*2*2=2^4*2$

since you need to calculate each of numbers ($2^1,2^2,2^3,2^4,2^5$), you can skip some of parts that you already calculated. When you calculate the $2^5$, you done have to calculate $2^4$ if that number $2^4$ is already calculated.
