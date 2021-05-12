---
layout: post
title:  "[JAVA] Reflection n Refactorying"
categories:
  - Computer
  - Java
tag:
- test 
---

### Reflection
<br>
　Reflection이란 **구체적인 클래스 타입을 알지 못해도**, 그 클래스의 메소드, 타입, 변수들을 접근할 수 있도록 해주는 `자바 API` 이다.  

　자바는 스크립트 언어가 아닌 컴파일 언이다. 원래 자바에서는 동적으로 객체를 생성하는 기술이 없었지만, 동적으로 인스턴스를 생성하는 Reflection이 그 역할을 대신한다. 즉, Reflection(투영, 반사)은 객체를 통해 클래스의 정보를 분석해내는 프로그램 기법이다.  

　자바 클래스 파일은 바이트 코트로 컴파일되어 Static 영역에 위치한다. 때문에 클래스 이름만 알고 있다면, 언제든 이 영역을 통해 클래스에 대한 정보를 가져올 수 있다. 아래는 가져올 수 있는 정보들이다.  

> ClassName <br> Class Modifiers (public, private, synchronized 등) <br> Package Info <br> SuperClass <br> Implemented Interfaces <br> Constructors <br> Methods Fields <br> Annotations

<br>

### Refactorying
<br>
　Refactorying이란 **외부 동작을 바꾸지 않으면서** 내부 구조를 개선하는 방법이다. 작은 단계로 나누어 프로그램을 변경하며, 코드가 작성된 후에 디자인을 개선하는 작업이다. 포인트는 리팩토링을 하면서 긴으을 추가하는 것이 아닌 기능 단위로 추가, 테스트 후 리팩토링을 진행해야 한다는 것이다.  

　이는 소프트웨어를 보다 이해하기 쉽고, 수정하기 쉽도록 만드는 것이다. 또한 겉으로 보이는 소프트웨어의 기능을 변경하지 않는 것에 그 목적이 있다.  

<br>

#### REFERENCE
Java Reflection 개념 및 사용법  
https://gyrfalcon.tistory.com/entry/Java-Reflection  
자바의 리플렉션  
https://brunch.co.kr/@kd4/8  
Refactorying 이란?  
https://nesoy.github.io/articles/2018-05/Refactoring  
{: .notice}