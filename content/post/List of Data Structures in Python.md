---
title : "List of Data Structures in Python"
date : "2021-09-15"
tags : [CodeStudy,Python,List,DataStructure]
topics : [CodeStudy]
---

## List

## Definition

- One of the data structure in python.
- Almost same as array in other languages.
- Object.

#### Data Structures in Python

1. List
2. Tuple
3. Dictionary
4. set

#### declaration

```python

temp=[]
temp=list()
temp=[5,9,44]
```

#### index structure

![](https://raw.githubusercontent.com/eunhanlee/img/main/0054.jpg)

#### characteristic

List in List is possible. This is same as 2D array in other languages
String in python is same as List

#### slicing

[starting index : ending index-1 : condition index]

- [0:8:3] = select index 0 to 7 by adding 3
- [:8:] = select index 0 to 7 by adding 1
- [7::] = select index 7 to -1 by adding 1
- [::-1] = select index 0 to -1 by adding -1

```python

a = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(a[0:8:3])  # [0, 3, 6]
print(a[:8:])  # [0, 1, 2, 3, 4, 5, 6, 7]
print(a[7::])  # [7, 8, 9]
print(a[::-1])  # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
```

#### Arithmetic Operation

```python

a=[1,2,3]
b=["apple","house","computer"]

print(a+b) # [1, 2, 3, 'apple', 'house', 'computer']
# print(a+3) # error
# print(a-b)  # error
# print(a-3) # error
# print(a*b) # error
print(b*3) # ['apple', 'house', 'computer', 'apple', 'house', 'computer', 'apple', 'house', 'computer']
print(b*0) # []
# print(a/b) # error
# print(a/3) # error
```

#### add element

- append() = add a new element behind
- extend() = add new elements behind
- insert() = add new elements by index
- [] = add new elements by index condition

```python

a=[1,2,3,4,5,6,7,8,9]
b=["apple","house","computer"]


a.append("test")
print(a) #[1, 2, 3, 4, 5, 6, 7, 8, 9, 'test']
a=[1,2,3,4,5,6,7,8,9]
a.append(b)
print(a) #[1, 2, 3, 4, 5, 6, 7, 8, 9, ['apple', 'house', 'computer']]
a=[1,2,3,4,5,6,7,8,9]
a.extend("test")
print(a) #[1, 2, 3, 4, 5, 6, 7, 8, 9, 't', 'e', 's', 't']
a=[1,2,3,4,5,6,7,8,9]
a.extend(b)
print(a) #[1, 2, 3, 4, 5, 6, 7, 8, 9, 'apple', 'house', 'computer']
a=[1,2,3,4,5,6,7,8,9]
a.insert(2,"test")
print(a) #[1, 2, 'test', 3, 4, 5, 6, 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
a.insert(2,b)
print(a) #[1, 2, ['apple', 'house', 'computer'], 3, 4, 5, 6, 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
a[3:]=b
print(a) #[1, 2, 3, 'apple', 'house', 'computer']
a=[1,2,3,4,5,6,7,8,9]
a[:4]=b
print(a) #['apple', 'house', 'computer', 5, 6, 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
a[6:6]=b
print(a) #[1, 2, 3, 4, 5, 6, 'apple', 'house', 'computer', 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
a[6:7]=b
print(a) #[1, 2, 3, 4, 5, 6, 'apple', 'house', 'computer', 8, 9]

```

#### delete element

- remove() = delete by value
- del = delete by index or list
- pop() = index or last one

```python

a=[1,2,3,4,5,6,7,8,9]
a.remove(1) # delete value 1
print(a) # [2, 3, 4, 5, 6, 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
# a.remove(98) # error
# print(a)
a=[1,2,3,4,5,6,7,8,9]
del a[3] # delete index 3
print(a) # [1, 2, 3, 5, 6, 7, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
del a[3:7] # delete index 3 to 6
print(a) # [1, 2, 3, 8, 9]
a=[1,2,3,4,5,6,7,8,9]
temp=a.pop() # return and delete the last element of the list
print(a) # [1, 2, 3, 4, 5, 6, 7, 8]
print(temp) # 9
a=[1,2,3,4,5,6,7,8,9]
temp=a.pop(1) # return and delete the index 1
print(a) # [1, 3, 4, 5, 6, 7, 8, 9]
print(temp) # 2
```
