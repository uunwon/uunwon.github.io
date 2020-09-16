---
layout: post
title:  "[Jump to Java] Multiplication table"
categories:
  - Code
tag:
- java
- code
---

<br>

## Multiplication table
### by Jump-to-Java

> 구구단을 구현해보자.

<p>
import java.util.*; <br>
<br>
public class multiplicationTable{ <br>
　　public static void main(String[] args){ <br>
　　　　Scanner sc = new Scanner(Sysete.in); <br>
　　　　int num; <br>
<br>
　　　　System.out.println("원하는 구구단은? "); <br>
　　　　num = sc.nextInt(); <br>
<br>
　　　　for(int i = 0;i < 9;i++){ <br>
　　　　　　System.out.print((num * (i+1)) + " "); <br>
　　　　} <br>
　　} <br>
}
</p>
{: .notice}

<br>

　💌 사이트의 소스에서 **toString()** 부분을 눈여겨보자. toString이 클래스 내에 선언되면 특별한 의미를 갖게 된다. new 키워드로 생성한 객체를 System.out.println 같은 걸로 출력했을 때 toString 메소드가 구현되어 있을 경우 toString) 메소드를 수행한 결과값을 리턴하게 된다. 

<br>

#### REFERENCE
https://wikidocs.net/236, 점프 투 자바
{: .notice}