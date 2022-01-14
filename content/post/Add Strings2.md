---
title : "Add Strings2"
date : "2021-09-10"
tags : [ProblemSolving,AddStrings]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/add-strings/ )

## My Answer

- 1 hour limit
- no search on internet

### My code

```java
class Solution {
    public String addStrings(String num1, String num2) {

        StringBuilder sb = new StringBuilder();

        int num1Leng = num1.length() - 1;
        int num2Leng = num2.length() - 1;

        int round = 0;

        for (int i = Math.max(num1.length(), num2.length()) - 1; i > -1; --i) {
            if (num1Leng < 0) {
                sb.append(String.valueOf(((num2.charAt(num2Leng) - 48) + round)%10));
                if ((((num2.charAt(num2Leng) - 48) + round)/10) > 0) {
                    round=1;
                }else{
                    round=0;
                }
            } else if (num2Leng < 0) {
                sb.append(String.valueOf(((num1.charAt(num1Leng) - 48) + round)%10));
                if ((((num1.charAt(num1Leng) - 48) + round)/10) > 0) {
                    round=1;
                }else{
                    round=0;
                }
            } else {
                sb.append(String.valueOf((((num1.charAt(num1Leng) - 48 + num2.charAt(num2Leng) - 48+round) % 10))));
                if ((((num1.charAt(num1Leng) - 48 + num2.charAt(num2Leng) - 48)+round) / 10) > 0) {
                    round=1;
                }else{
                    round=0;
                }
            }

            --num1Leng;
            --num2Leng;

        }
        
        if(round != 0){
            sb.append("1");
        }

                      
        return sb.reverse().toString();
        
    }
}
```
- Time complexity : <span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>O</mi><mo stretchy="false">(</mo><mi>m</mi><mi>a</mi><mi>x</mi><mo stretchy="false">(</mo><mi>n</mi><mo separator="true">,</mo><mi>m</mi><mo stretchy="false">)</mo><mo stretchy="false">)</mo></mrow><annotation encoding="application/x-tex">O(max(n,m))</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:1em;vertical-align:-0.25em;"></span><span class="mord mathdefault" style="margin-right:0.02778em;">O</span><span class="mopen">(</span><span class="mord mathdefault">m</span><span class="mord mathdefault">a</span><span class="mord mathdefault">x</span><span class="mopen">(</span><span class="mord mathdefault">n</span><span class="mpunct">,</span><span class="mspace" style="margin-right:0.16666666666666666em;"></span><span class="mord mathdefault">m</span><span class="mclose">)</span><span class="mclose">)</span></span></span></span>
- Space complexity : $O(1)$

### My result
- Runtime: 4 ms, faster than 32.72% of Java online submissions for Add Strings.
- Memory Usage: 40.8 MB, less than 5.11% of Java online submissions for Add Strings.

---

## Best Answer
Search from internet and modify
```java

class Solution {
    public String addStrings(String num1, String num2) {

        StringBuilder sb = new StringBuilder();
        int index1 = num1.length() - 1;
        int index2 = num2.length() - 1;
        int round = 0;

//if both index are -1, stop loop. otherwise, keep loop
//start from the end of the list for addtion
        while (index1 >= 0 || index2 >= 0) {
            int temp1 = index1 < 0 ? 0 : num1.charAt(index1) - '0';//if index is -1, put 0 if not, put number
            int temp2 = index2 < 0 ? 0 : num2.charAt(index2) - '0';//if index is -1, put 0 if not, put number

            sb.insert(0, (temp1 + temp2 + round) % 10);//insert number without carry at the most left
            round = (temp1 + temp2 + round) / 10;//save carried number for next loop

            --index1;
            --index2;
        }

       if(round != 0){//If last addtion has carry, add them
            sb.insert(0,"1");
        }
        return sb.toString();//stringBuilder to String and return
    }
}
```
- Time complexity : $O(max(n,m))$
- Space complexity : $O(1)$


## Reflect on
- Basic algorithm and using stringBuilder was correct. However, my code is not optimizated.
- ternary conditional operator is only possible to use higher than Java 8
- Code readability is much better
