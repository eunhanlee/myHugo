---
title : "stable vs. unstable sorts"
date : "2021-04-08"
tags : [coding questions, sort, stable sort, unstable sort]
topics : [CodingQuestions]
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
System.out.println(x * ++y);//x=2, y=3 add first so, y=4 then print 8(=2*4)
```

## conclusion

- **++i** wil give you slightly better speed and memory. 
- i++ will happen **after** run the code
- ++i will happen **before** run the code