---
title : "Basic Search Algorithms"
date : "2021-09-03"
tags : [CodeStudy,SearchAlgorithm,LinearSearch,BinarySearch,Hashing]
topics : [CodeStudy]
---

## Basic Search Algorithm
1. Linear Search
2. Binary Search
3. Hashing 


### Linear Search
#### Definition
check all of the list one by one.
#### Time complexity
O(n)
#### Points
- It does not matter about date type
- need memory space as total list n

### Binary Search
#### Definition
check middle of list first. if the number is smaller than what you are looking for, check right side only and doing this continuously. It will decrease search list in half.
#### Time complexity
O(log n)
#### Points
- pre-condition : the list sorted
- pre-condition : when new data inserted, need to sort
- Since it need to sort when new data inserted, it can be very slow if there are a lot of insertion
- one of divide-and-conquer technique

### Hashing 
#### Definition
By using hash code, find the value.
Usually, use Hash map or Hash table
#### Time complexity
O(1)
#### Points
- It does not matter about date type
- It need more memories than total list n
- The worst case, hashing can be slow because of hash collision


## Result
Search more than Insert -> Binary Search
Insert more than Search -> Linear Search
use more space to faster -> hashing
