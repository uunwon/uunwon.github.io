---
layout: post
title:  "[Jump to Java] Multiples of 3 and 5"
categories:
  - Code
tag:
- java
- code
---

## Multiples of 3 and 5
#### by Jump-to-Java
<br>

프로젝트 오일러에서 제공하는 첫번째 퀴즈,  

> 10 미만의 자연수에서 3과 5의 배수를 구하면 3, 5, 6, 9이다. 이들의 총합은 23이다. 1000미만의 자연수에서 3, 5의 배수의 총합을 구하라.

<p>
public class multiplesof3and5{ <br>
　　int max; <br>
    <br>
　　public multiplesof3and5(int max){ <br>
　　　　this.max = max; <br>
　　} <br>
　　<br>
　　public int sum(){ <br>
　　　　int sum = 0; <br>
　　　　for(int i = 0;i < max;i++){ <br>
　　　　　　if((i % 3 == 0) || (i % 5) == 0){ <br>
　　　　　　　　sum += i; <br>
　　　　　　} <br>
　　　　} <br>
　　　　return sum; <br>
　　} <br>
    <br>
　　public static void main(String[] args){ <br>
　　　　System.out.println(new multiplesof3and5(10).sum()); <br>
　　　　System.out.println(new multiplesof3and5(1000).sum()); <br>
　　} <br>
}
</p>
{: .notice}

<br>

#### REFERENCE
https://wikidocs.net/237, 점프 투 자바
{: .notice}