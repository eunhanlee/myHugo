---
title : "Set of Data Structures in Python"
date : "2021-11-17"
tags : [CodeStudy,Python,Set,DataStructure]
topics : [CodeStudy]
---

## Set

## Definition

- One of the data structure in python.
- Create set of data

#### Data Structures in Python

1. List: [ ]
2. Tuple: ( )
3. Dictionary: { key : value }
4. set: { }

#### declaration

- use { and } to declare

```python

setA={1,3,4,"test"} # {1, 'test', 3, 4}
setB={2,4,"test",5,6} # {2, 'test', 4, 5, 6}
```

#### Characteristics

- No duplicated value
- Do not care about order
- set algebra(union, intersection, difference, symmetric difference)

## Set Algebra

#### union

![](https://raw.githubusercontent.com/eunhanlee/img/main/0060.jpg)
Keyword: "|", "union()"

#### union example

```python

setA={1,3,4,"test"} # {1, 'test', 3, 4}
setB={2,4,"test",5,6} # {2, 'test', 4, 5, 6}


print(setA|setB)
print(setA.union(setB))
# {1, 2, 3, 4, 5, 6, 'test'}
```

#### intersection

![](https://raw.githubusercontent.com/eunhanlee/img/main/0061.jpg)

Keyword: "&","intersection()"

#### intersection example

```python

setA={1,3,4,"test"} # {1, 'test', 3, 4}
setB={2,4,"test",5,6} # {2, 'test', 4, 5, 6}

print(setA&setB)
print(setA.intersection(setB))
# {'test', 4}
```

#### difference of sets

![](https://raw.githubusercontent.com/eunhanlee/img/main/0059.jpg)

Keyword: "-","difference()"

#### difference of sets example

```python

setA={1,3,4,"test"} # {1, 'test', 3, 4}
setB={2,4,"test",5,6} # {2, 'test', 4, 5, 6}

print(setA-setB)
print(setA.difference(setB))
# {1, 3}
```

#### symmetric difference

![](https://raw.githubusercontent.com/eunhanlee/img/main/0058.jpg)

Keyword: "^","symmetric_difference()"

#### symmetric difference example

```python

setA={1,3,4,"test"} # {1, 'test', 3, 4}
setB={2,4,"test",5,6} # {2, 'test', 4, 5, 6}

print(setA^setB)
print(setA.symmetric_difference(setB))
# {1, 2, 3, 5, 6}

```
