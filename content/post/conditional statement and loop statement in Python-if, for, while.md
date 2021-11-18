---
title : "conditional and loop statement in Python-if, for, while"
date : "2021-11-18"
tags : [CodeStudy,Python,ConditionalStatement,LoopStatement]
topics : [CodeStudy]
---

## conditional statement and loop statement in Python
### conditional statement (if statement)
#### One Condition
- Keyword: if

if [condition] :
[space]code you want to learn

#### Multiple Condition
- Keyword: elif
- if must there before use elif
if [condition] :
[space]code you want to learn
elif [condition] :
[space]code you want to learn
elif [condition] :
[space]code you want to learn

#### Other than Condition
- Keyword: else
- if must there before use else
if [condition] :
[space]code you want to learn
else :
[space]code you want to learn


### if Statement Example
```python
a = 3
if a > 5:
    print("a is bigger than 5")
elif a > 0:
    print("a is bigger than 0 but smaller than 5")
else:
    print("a is negative")
```
### Loop Statement (for Statement)
#### Repeat Example
- 10 times loop
```python
for i in range(10): 
    print("Hi")
```
#### list loop Example
- Repeat as much as elements in list
```python
a = ["A", "B", "C"]
for i in a:
    print(i)
# A B C
```
#### list loop with index Example
- Repeat as much as elements in list
```python
for i, j in enumerate(a):
    print(i, ":", j)
# 0 : A
# 1 : B
# 2 : C
```
#### add two list and loop Example
- The pair's data type is tuple
```python
numbers = [9, 7, 7]
letters = ["z", "x", "y"]
for pair in zip(numbers, letters):
    print(pair)
# (9, 'z')
# (7, 'x')
# (7, 'y')
```
#### Loop with certain index Example
- 5 to 9
```python
for i in range(5, 10):  # 5 ~ 9
    print("Hello", i)
# Hello 5
# Hello 6
# Hello 7
# Hello 8
# Hello 9
```
#### loop until certain condition
- loop until i is "o"
```python
a = "balloon"

for i in a:
    print(i)
    if i == "o":
        break
# b a l l o
```


### Loop Statement (while Statement)
#### loop until certain condition
- loop until i is bigger than 5
```python
i = 0
while i < 5:
    print(i)
    i = i + 1
# 0 1 2 3 4
```