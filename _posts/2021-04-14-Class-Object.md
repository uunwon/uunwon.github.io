---
layout: post
title:  "[JAVA] Class, Object, Instance"
categories:
  - Computer
tag:
- java 
---

## Class, Object, Instance 

* 객체지향 프로그래밍(OOP) 등장 배경
* 클래스 (Class)
* 객체 (Object)
* 인스턴스 (Instance) 
<br>

<hr>

### 🎯 객체 지향 등장 배경
<br>
　**객체지향 프로그래밍(OOP, Object-Oriented Programming)**은 컴퓨터 프로그래밍의 패러다임의 하나이다. 이는 컴퓨터 프로그램을 명령어의 목록으로 보는 시각에서 벗어나 여러 개의 독립된 단위, 즉 '객체'들의 모임으로 파악하고자 하는 것이다. 객체지향 프로그래밍은 프로그램을 유연하고 변경이 용이하게 만들기 때문에 대규모 소프트웨어 개발에 많이 사용된다. 

　프로그램을 단순히 데이터와 처리 방법으로 나누는 것이 아니라, 프로그램을 수많은 '객체'라는 기본 단위로 나누고 이 객체들의 상호작용으로 서술하는 방식이다. 객체를 데이터의 묶음으로만 착각하기 쉬운데, 그보다는 하나의 '역할'을 수행하는 메소드와 데이터의 묶음으로 봐야한다.

> 코드의 재사용성이 높다 <br> 코드의 관리가 용이하다 <br> 신뢰성이 높은 프로그래밍을 가능하게 한다

<br>

### 🔑 Class
　객체를 만들어내기 위한 설계도 혹은 틀  
　연관되어 있는 변수와 메서드의 집합  
　-> 클래스란 객체를 정의해놓은 것으로써, 객체를 생성하는데 사용된다.  

<br>

### 🪓 Object
　소프트웨어 세계에 구현할 대상  
　클래스에 선언된 모양 그대로 생성된 실체  
　-> 클래스의 인스턴스라고도 부르며, 모든 인스턴스를 대표하는 포괄적인 의미를 가진다. oop의 관점에서 **클래스의 타입**으로 선언되었을 때 '객체'라고 부른다.  

<br>

### 🔨 Instance
　설계도를 바탕으로 소프트웨어 세계에 구현된 구체적인 실체  
　객체를 소프트웨어에 실체화한 것
　실체화된 인스턴스는 메모리에 할당됨    
　-> oop의 관점에서 **객체가 메모리에 할당**되어 실제 사용될 때 '인스턴스'라 부르며, 추상적인 개념과 구체적인 객체 사이의 **관계**에 초점을 맞출 경우에 '~의 인스턴스' 형태로 사용된다.  

<p>
/* 클래스 */ <br>
public class Animal{ <br>
　　... <br>
 } <br>
/* 객체와 인스턴스 */ <br>
public class Main { <br>
　public static void main(String[] args) <br>
　　　　Animal cat, dog; // '객체' <br>
　　　　// 인스턴스화 <br>
　　　　cat = new Animal(); // cat은 Animal 클래스의 '인스턴스' (객체를 메모리에 할당) <br>
　　} <br>
}
</p>
{: .notice}

<br>

#### REFERENCE
객체지향 프로그래밍의 정의와 탄생배경  
https://dduddublog.tistory.com/8  
객체지향의 등장 배경과 이해  
https://limsungju.tistory.com/13  
[Java] 클래스, 객체, 인스턴스의 차이  
https://gmlwjd9405.github.io/2018/09/17/class-object-instance.html <br>