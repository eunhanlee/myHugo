---
title : "[JAVA code]hashmap"
date : "2021-04-12"
tags : [Java Dictionary,hashmap]
topics : [Java]
---

```java

private HashMap<Character, Character> map;
this.map = new HashMap<>();
```
```java

HashMap<String,String> map = new HashMap<>(map1);// HashMap that has same key and values as map1
HashMap<String,String> map2 = new HashMap<>(10);// set capacity defult is 16
map.put("a","b"); //add
map.get("a");//if not there, return null
map.getOrDefault("a","no value");//if not there, return 2nd parameter "no value"
map.isEmpty()//T or F for all data
map.size() //return how may keys
map.containsKey( key )//check key is there
map.containsValue( value )//check value is there
map.remove("a");
map.clear(); //delete all keys and values
```

## out
```java

System.out.println(map); //print like : {1=apple, 2=seven, 3=dark}
```
```java	
//entrySet().iterator()
Iterator<Entry<Integer, String>> entries = map.entrySet().iterator();
while(entries.hasNext()){
    Map.Entry<Integer, String> entry = entries.next();
    System.out.println("[Key]:" + entry.getKey() + " [Value]:" +  entry.getValue());
}
```
```java	
//keySet().iterator()
Iterator<Integer> keys = map.keySet().iterator();
while(keys.hasNext()){
    int key = keys.next();
    System.out.println("[Key]:" + key + " [Value]:" +  map.get(key));
}
```
