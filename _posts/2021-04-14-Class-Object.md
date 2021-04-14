---
layout: post
title:  "Class, Object, Instance"
categories:
  - Computer
tag:
- java 
---

## Class, Object, Instance 

* 클래스 (Class)
* 객체 (Object)
* 인스턴스 (Instance) 

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
https://gmlwjd9405.github.io/2018/09/17/class-object-instance.html <br>