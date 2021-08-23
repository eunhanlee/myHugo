---
title : "what happen if + or - with Char in JAVA"
date : "2021-08-23"
tags : [CodeStudy, Char, +, -, Java]
topics : [CodeStudy]
---

## Result

| code | result |
|---|---|
| char type + int type | return unicode |
| char type - int type | error |
| int type + char type | return unicode |
| int type - char type | error |
| char type + char type | return unicode |
| char type - char type | return unicode |

- String is not Primitive Data Type. This is object

## example of use

### For lexicographical order

```java

for (int i = 0; i < order.length(); ++i)
            index[order.charAt(i) - 'a'] = i;
```

## Primitive Data Types

According to [Primitive Data Types Java API](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html)

The Java programming language is statically-typed, which means that all variables must first be declared before they can be used. This involves stating the variable's type and name, as you've already seen:

`int gear = 1;`

Doing so tells your program that a field named "gear" exists, holds numerical data, and has an initial value of "1". A variable's data type determines the values it may contain, plus the operations that may be performed on it. In addition to `int`, the Java programming language supports seven other primitive data types. A primitive type is predefined by the language and is named by a reserved keyword. Primitive values do not share state with other primitive values. The eight primitive data types supported by the Java programming language are:

### char:

The char data type is a single 16-bit Unicode character. It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive).

## Test

```java

public class Main {
    public static void main(String[] args) {

        String temp="apple";
        char a = 'A';// unicode 65
        char b = 'B';// unicode 66
        System.out.println(a);
        System.out.println(a+0);
        System.out.println(a-b);
        System.out.println(a + 5);
        System.out.println(5 + a);
        System.out.println(5 + a+temp);
//        System.out.println("a - 5->"+a - 5);
//        System.out.println("5 - a->"+5 - a);
        System.out.println(a + temp.charAt(1));
        System.out.println(temp.charAt(1)+a);
        System.out.println(a + a);
        System.out.println(a + temp);

    }
}
```

## Output

```java

A
65
-1
70
70
70apple
//error: java: bad operand types for binary operator '-'
//error: java: bad operand types for binary operator '-'
177
177
130
Aapple
```