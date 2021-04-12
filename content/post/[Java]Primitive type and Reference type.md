---
title : "[Java]Primitive type and Reference type"
date : "2021-04-12"
tags : [code knowledge, Primitive type, Primitive,Reference type,Reference,Java]
topics : [CodeKnowledge]
---

## Primitive type

- JAVA provides 8 kinds of Primitive type
- There is no null value. Defult value is already inserted.
- **actual value** will saved in **Stack** memory.
- String is object. Not primitive type.

| Data Type | Allocated Memory | Defult Value | Range of Data                                          | Range of Data in Number                    |
| :--------- | :---------------- | :------------ | :------------------------------------------------------ | :------------------------------------------ |
| boolean   | 1 byte           | false        | true, false                                            |
| byte      | 1 byte           | 0            | -127 ~ 128                                             | $-2^{7}$~ $(2^{7}-1)$                      |
| short     | 2 byte           | 0            | -32,768 ~ 32,767                                       | $-2^{15}$~ $(2^{15}-1)$                    |
| int       | 4 byte           | 0            | -2,147,483,648 ~ 2,147,483,647                         | $-2^{31}$~ $(2^{31}-1)$                    |
| long      | 8 byte           | 0L           | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 | $-2^{63}$~ $(2^{63}-1)$                    |
| float     | 4 byte           | 0.0F         | 0.000...0034 ~ 3400...000                              | $3.4 \cdot 10^{-38}$ ~ $3.4 \cdot 10^{38}$ |
| double    | 8 byte           | 0            | 0.00000000...00017 ~ 17000...000000000                 | $1.7 \cdot 10^{-308}$~$1.7 \cdot 10^{308}$ |
| char      | 2 byte           | '\u0000'     | 0~65,535                                               | $0$ ~ $(2^{16}-1)$                         |

## Reference type

- Every type except the primitive type is Reference type
- There is null value
- **actual address** will saved in **Heap** memory.

| Data Type   | Allocated Memory | Defult Value |
| ----------- | ---------------- | ------------ |
| Array       | 4 byte           | NULL         |
| Enumeration | 4 byte           | NULL         |
| Class       | 4 byte           | NULL         |
| Interface   | 4 byte           | NULL         |
