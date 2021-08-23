---
title : "Primitive type and Reference type in Java"
date : "2021-08-23"
tags : [CodeStudy, Java, PrimitiveType, ReferenceType]
topics : [CodeStudy]
---

# Kinds of Data Type in Java

## Primitive type

- Java provides 8 kinds of Primitive type.
- Primitive data types cannot contain **null**
- **actual value** will saved in **Stack** memory.

| data type | base memory | defult value |range of data| range of data in number|
| --------- | ---------------- | ------------ | ------------------------------------------------------ | ------------------------------------------ |
| boolean   | 1 byte           | false        | true, false                                            |true, false|
| byte      | 1 byte           | 0            | -127 ~ 128                                             | $-2^{7}$~ $(2^{7}-1)$                      |
| short     | 2 byte           | 0            | -32,768 ~ 32,767                                       | $-2^{15}$~ $(2^{15}-1)$                    |
| int       | 4 byte           | 0            | -2,147,483,648 ~ 2,147,483,647                         | $-2^{31}$~ $(2^{31}-1)$                    |
| long      | 8 byte           | 0L           | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 | $-2^{63}$~ $(2^{63}-1)$                    |
| float     | 4 byte           | 0.0F         | 0.000...0034 ~ 3400...000                              | $3.4 \cdot 10^{-38}$ ~ $3.4 \cdot 10^{38}$ |
| double    | 8 byte           | 0            | 0.00000000...00017 ~ 17000...000000000                 | $1.7 \cdot 10^{-308}$~$1.7 \cdot 10^{308}$ |
| char      | 2 byte           | '\u0000'     | 0~65,535                                               | $0$ ~ $(2^{16}-1)$                         |



## Reference type

- If not primitive type, it is Reference type.
- Reference data types can contain **null**
- **address** will saved in **Heap** memory.

| data type | base memory | defult value |
| -------- | ------ | -------- | 
|Array|4 byte |NULL
| Enumeration|4 byte |NULL
|Class|4 byte |NULL
|Interface |4 byte |NULL
