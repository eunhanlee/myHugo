---
title : "[JAVA code]switch"
date : "2021-04-12"
tags : [Java Dictionary,switch,switch statement]
topics : [Java]
---

### lambda Example (after java 8)
```java

public static double calculate(String operator, double x, double y) {
    return switch (operator) {
        case "+","add" -> x + y;
        case "-","sub" -> x - y;
        case "*","multiply" -> x * y;
        case "/","divide" -> {
            if (y == 0) {
                throw new IllegalArgumentException("Can't divide by 0");
            }
            yield x / y;
        }
        default -> throw new IllegalArgumentException("Unknown operator "+operator);
    };
}
```

### Example
```java

    public static double calculate(String operator, double x, double y) {
        switch (operator) {
            case "+":
            case "add":
                return x + y;
            case "-":
            case "sub":
                return x - y;
            case "*":
            case "multiply":
                return x * y;
            case "/":
            case "divide":
                if (y == 0) {
                    throw new IllegalArgumentException("Can't divide by 0");
                }
                return x / y;
            default:
                throw new IllegalArgumentException("Unknown operator " + operator);
        }
    }
```
