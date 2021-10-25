---
title : "Tuple of Data Structures in Python"
date : "2021-10-25"
tags : [CodeStudy,Python,Tuple,DataStructure]
topics : [CodeStudy]
---

## Tuple

## Definition

- One of the data structure in python.
- Almost same as List But Tuple is not editable.
- Object.

#### Data Structures in Python

1. List
2. Tuple
3. Dictionary
4. set

#### declaration
use "(" and ")" to declear.
But, if there is a element in Tuple, you need to add comma

```python

tuple1=(1,)
tuple2=(1,2,3)
notTuple=(0) #wrong, this is int type. comma needed
```

#### index structure
same as List

![](https://raw.githubusercontent.com/eunhanlee/img/main/0054.jpg)

#### characteristic

Tuple is not editable.

#### slicing
Same as List.

[starting index : ending index-1 : condition index]

- [0:8:3] = select index 0 to 7 by adding 3
- [:8:] = select index 0 to 7 by adding 1
- [7::] = select index 7 to -1 by adding 1
- [::-1] = select index 0 to -1 by adding -1

```python

a = (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
print(a[0:8:3])  # (0, 3, 6)
print(a[:8:])  # (0, 1, 2, 3, 4, 5, 6, 7)
print(a[7::])  # (7, 8, 9)
print(a[::-1])  # (9, 8, 7, 6, 5, 4, 3, 2, 1, 0)
```