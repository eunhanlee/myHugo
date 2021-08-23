---
title : "[JavaException]IllegalArgumentException"
date : "2021-08-23"
tags : [CodeDictionary, Java, Exception, IllegalArgumentException]
topics : [CodeDictionary]
---

## Reason
Thrown to indicate that a method has been passed an illegal or inappropriate argument.


argument is actual values that are passed to variables
If you put any actual values that is not correct for the variable, it will cause IllegalArgumentException

## Example
```java

int a = 2147483649; // value is too big
int a = -2147483649; // value is too small

String date="08-07-1990"; // format is dd-MM-yyyy
Date format=new SimpleDateFormat("dd/MM/yyyy").parse(date);// format is different

````

## Solution

- check input value range
- check calculation that can be over the variable limitation
- use try-catch block
