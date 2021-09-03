---
title : "Arithmetic Operation in Python"
date : "2021-09-03"
tags : [CodeStudy,Python,ArithmeticOperation]
topics : [CodeStudy]
---


## kinds of Arithmetic Operation in Python
|Symbol|explaination|return
|---|---|---|
|+|Addition|depend on input type|
|-|Subtraction|depend on input type|
|*|Multiplication|depend on input type|
|/|Division|real number
|//|Division|Integer
|%|Remaineder|real number
|**|power of|depend on input type
|and|and logic gare|T or F|
|or| or logic gate|T or F|
|<|less than|T or F|
|>|greater than|T or F|
|<=|less than or equal|T or F|
|>=|greater than or equal|T or F|
|==|equal|T or F|

## Result

### +, -, *, /, //, %, **, <, >, <=, >= table

A|B|result
|---|---|---|
int|int|int A+B result
int|float|float A+B result
int|bool-T|int A+1 result
int|bool-F|int A+0 result
int|none|TypeError
int|String|TypeError
float|bool-T|float A+1 result
float|bool-F|float A+0 result
float|none| TypeError
float|String|TypeError
bool|none|TypeError
bool|String|TypeError
none|String|TypeError

When computer created and programming language started, 1 was true and 0 was false. 

### == table

A|B|result
|---|---|---|
int|int| bool result
int|float| bool result
int|bool| bool result
int|none| bool result
int|String| bool result
float|bool| bool result
float|none| bool result
float|String| bool result
bool|none| bool result
bool|String| bool result
none|String| bool result

unlike Java, this is not comparing class. it compare values.

### and, or truth table
A|B|and|or|
|---|---|---|---|
|F|F|F|F
|F|T|F|T
|T|F|F|T
|T|T|T|T


As above table, the "and" "or" are for true and false. 
If you put other type, or gate return B value
If you put other type, and gate return A value

