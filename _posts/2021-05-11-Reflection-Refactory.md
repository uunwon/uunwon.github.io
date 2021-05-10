---
layout: post
title:  "[자바] 리플렉션과 리팩토링"
categories:
  - Computer
  - Java
tag:
- test 
---

### 리플렉션

　Reflection이란 **구체적인 클래스 타입을 알지 못해도**, 그 클래스의 메소드, 타입, 변수들을 접근할 수 있도록 해주는 `자바 API` 이다.  

　자바는 스크립트 언어가 아닌 컴파일 언이다. 원래 자바에서는 동적으로 객체를 생성하는 기술이 없었지만, 동적으로 인스턴스를 생성하는 Reflection이 그 역할을 대신한다. 즉, Reflection(투영, 반사)은 객체를 통해 클래스의 정보를 분석해내는 프로그램 기법이다.  

　자바 클래스 파일은 바이트 코트로 컴파일되어 Static 영역에 위치한다. 때문에 클래스 이름만 알고 있다면, 언제든 이 영역을 통해 클래스에 대한 정보를 가져올 수 있다. 아래는 가져올 수 있는 정보들이다.  

> ClassName <br> Class Modifiers (public, private, synchronized 등) <br> Package Info <br> SuperClass <br> Implemented Interfaces <br> Constructors <br> Methods Fields <br> Annotations

<br>

### Apache PHP MySQL
<br>
　**A** pache : 웹 서버  