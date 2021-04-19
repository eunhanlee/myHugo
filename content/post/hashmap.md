---
title : "what is hashmap in Java"
date : "2021-04-19"
tags : [code knowledge,Hashmap,hash,Java]
topics : [CodeKnowledge]
---



## Definition

Hashmap basically solves the problem of searching objects from large set.

## When should we use it

- large set of objects
- frequent access to objects required.

## methods

|method|result|time complexity|
|---|---|---|
|`HashMap<String,String> map = new HashMap<>();`|create hashmap|constructor
|put( key, value )|add key and value|usually O(1)
|remove( key )|remove the key|usually O(1)
|get( key )|get value from the key|usually O(1)
|isEmpty()|T or F for all data|O(n)
|size()|return how may keys|O(n)
|containsKey( key )|check key is there|usually O(1)
|containsValue( value )|check value is there|usually O(1)
|getOrDefault( key, value)|get value from the key. if key is not there return value from method|usually O(1)

## consist of

- array
- linkedList

## characteristics

- key and value set
- null value is fine
- keys cannot be same but value is fine
- HashMap added new space with twice like List. For example, origianl hashmap have 4 spaces and if you add 5 values, the hashmap will have 8 spaces. Therefore, set numbers of data when create the hashmap.
- Not thread safe. thread safe is for hash table. (collection framework trying to merge the hash table and hashmap. But currently still have some issues.02-23-2021)

```java
HashMap<String,String> map = new HashMap<>(10);
```

## Basic process
 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0010.png)

## example

#### 1. put "aaa", ""ccc" pair into hashmap

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0011.png)

#### 2. put key, "AAA" into the box labeled as A

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0012.png)

#### 3. compute "AAA" with some math process and get result. If the result is "B"

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0013.png)


#### 4. put the value "ccc" into "B" box.

 ![](https://raw.githubusercontent.com/eunhanlee/img/main/0014.png)


### process of put method

hashMap.put("a","b");

1. check the hash table already have hashcode of the key, "a"
2. if there is no same key, new key-value pair will created and put it
3. if there is same key, replace the value to "b"

### process of get method

hashMap.get("a");

1. check the hash table already have hashcode of the key, "a"
2. if there is no same key, return null
3. if there is same key, return the value, "b"

## why time complexity is not always O(1)?

The hash code can be duplicated from two different keys. The math process meant to create all different numbers but, sometimes it create same address.    
For example, hash code of "g" and "h" both can create hash code "u" and this case the value may go to same address. In this case, the code will automatically find other address that did not use. Thus, in worst case, it will be O(n).