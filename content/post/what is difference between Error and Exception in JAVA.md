---
title : "what is difference between Error and Exception in Java"
date : "2021-08-23"
tags : [CodeStudy, Java, Error, Exception, Difference]
topics : [CodeStudy]
---

## What is Error

Programs run something that is not what programmers wanted or shutdown unexpectedly.
Any causes of that action are Error.

## Kinds of Errors

### compile-time error 
compile failed. usually, wrong lanuage keyword used. python does not understand "System.out.println" This code is for JAVA.

### runtime error
crash during the programs run. put values in int arr[5] that array size is 3

### logical error
programmer created wrong process. you wanted to put blue in variable x. But, you accidently put green

## Error vs. Exception in Java

**Error**: created by computer hardware
**Exception**: created by computer software

Thus, Error is created by compiler or computer graphics card. programmer not much things to do
However, the Exception is created by program, or wrong command. 

## exception handling

Def. : protect from unexpected happens
Purpose : keep programs run well 

## Exception in Java

![](https://raw.githubusercontent.com/eunhanlee/img/main/0040_Exception_in_Java.png)

In java, computer do not check the Exceptions under the runtimeException. Thus, we need to study them.