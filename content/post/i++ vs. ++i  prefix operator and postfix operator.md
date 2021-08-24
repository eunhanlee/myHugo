---
title : "i++ vs. ++i  prefix operator and postfix operator"
date : "2021-08-24"
tags : [CodeStudy, prefixOperator, postfixOperator, prefix, postfix, operator,++,--]
topics : [CodeStudy]
---

|code|name|How|
|---|---|---|
++i|prefix increment operator|`i = i+1;`<br>`return i;`|
i++|postfix increment operator|`final int t = i;` <br> `i = i+1;` <br>`return t;`|
--i|prefix decrement operator|`i = i-1;`<br>`return i;`|
i--|postfix decrement operator|`final int t = i;` <br> `i = i-1;` <br>`return t;`|




```java
int x = 2;
int y = 2;
  
System.out.println(x * y++);// x=2, y=2 add later so, print 4(=2*2) then y =3
System.out.println(x * y++);// x=2, y=3 add later so, print 6(=2*3) then y =4
```

```java
int x = 2;
int y = 2;
  
System.out.println(x * ++y);//x=2, y=2 add first so, y=3 then print 6(=2*3)
```

## conclusion

- **++i** wil give you slightly better speed and memory.    If you are working with backend(Java), this is not important. However, if you are working with console games(C++), this is important.
- i++ will happen **after** run the code
- ++i will happen **before** run the code