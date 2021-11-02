---
title : "what is enum class in Java"
date : "2021-11-02"
tags : [CodeStudy, Java, Enum, Enumeration, EnumeratedType]
topics : [CodeStudy]
---

## Definition
enum class is for define constant. 
It will contain the value that will not change during the program is working

## Reason for using the enum class
Sometimes, the program need constant value that should not changed. We use enum class for define the value.
We calls, "define Constant"

## History
The notion of constant is came from C language.
C used define Preprocessor and const keyward. 

#### C code example
```c

#include <stdio.h>

#define MALE 1 // #define Preprocessor 

int main()
{
    const int FEMALE = 2; // const keyward
    
    int input = 2;
    
    if(input==MALE){
        printf("I am male");
    }else{
        printf("I am Female");
    }

    return 0;
}
```
#### result
```c
I am Female
```
if you put 3 in input variable, it still print, "I am Female" We need additional if statement for checking the issue.

In Java, we started use "final." The final is not exactly same as the Preprocessor, But we used it with static final keyward
#### java code example
```java

public class Main {

    public static final String MALE = "MALE";
    public static final String FEMALE = "FEMALE";

    public static void main(String[] args) {
        String gender;
        gender = Main.MALE;
        gender = "male"; //mistake, but no error
                
        if(gender.equals(Main.MALE)){
            System.out.println("I am male");
        }else{
            System.out.println("I am female");
        }        

    }
} 
```
#### result
```java
I am female
```

Howver, still same issue stated. The constant's data type is String and it caused wrong result.

Thus, we use enum class since java 1.5.
We calls, "enumeration", "enumerated type", and "enum"

#### enum java code example
```java
public class Main {

    public static void main(String[] args) {
        Gender gender;
        gender = Gender.MALE;
        gender = "male"; //mistake, but it shows error

        if(gender==Gender.MALE){
            System.out.println("I am male");
        }else{
            System.out.println("I am female");
        }

    }
}

enum Gender {MALE, FEMALE;}
```