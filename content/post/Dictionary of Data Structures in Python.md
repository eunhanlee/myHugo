---
title : "Dictionary of Data Structures in Python"
date : "2021-11-03"
tags : [CodeStudy,Python,Dictionary,DataStructure]
topics : [CodeStudy]
---

## Dictionary

## Definition

- One of the data structure in python.
- has key and value bined. You can fine value when you know the key
- very slimier with hashmap

#### Data Structures in Python

1. List
2. Tuple
3. Dictionary
4. set

#### declaration
- use { and } to declare
- the value can be list
- the key can be int or string. But not list. (TypeError: unhashable type: 'list')

```python

dictionary={"key1":"value1","key2":"value2","key3":"value3"}
```

#### how to use
1. indexing like List
2. get() method

##### difference between the indexing and get method
If key does not exist, the indexing will return error. But get method will return None.

```python
# List처럼 인덱스를 넣기
print(dictionary["key1"]) # value1
print(dictionary["key2"]) # value2
print(dictionary["key3"]) # value3
# print(dictionary["key4"]) # KeyError: 'key4' means there is no key

# get() 메서드를 사용
print(dictionary.get("key1")) # value1
print(dictionary.get("key2")) # value2
print(dictionary.get("key3")) # value3
print(dictionary.get("key4")) # return None, it does not cause error
```

