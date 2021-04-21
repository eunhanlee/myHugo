---
title : "[Java]Stringbuilder"
date : "2021-04-21"
tags : [code knowledge, Stringbuilder,Java]
topics : [CodeKnowledge]
---

## Definition

StringBuilder class is for attach additional strings after you created the String.

## Why should we use Stringbuilder?

We can add Strings various ways.
- concat : `word.concat("add");`
- using "+" : `word += "add";`

However, String is object and it is immutable. What happen in computer is make another space and copy and paste the original string and add new strings. If we change the string more than 1000 times, it will be slow and waste memory.

Therefore, 

if you need to change String frequently, use StringBuilder.

If you need to change String frequently on muti-threaded environment, use StringBuffer.


## Example

when capacity increases the capacity by (oldcapacity*2)+2.
```java
StringBuilder sb = new StringBuilder();
```

```java
        sb.append("aaa"); // add aaa
        sb.insert(1, "ccc"); // add at position acccaa
        sb.delete(3, 5); // delete at position skip the end acca
        sb.indexOf("ca");// if can't find, -1
        sb.substring(0, 4);  //
        sb.length(); 
        sb.reverse();
        sb.replace(0, 2, "ddd");//delete that s and e insert word
        sb.toString(); //sb is object set String
```
