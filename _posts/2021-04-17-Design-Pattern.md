---
layout: post
title:  "Design Pattern"
categories:
  - Computer
tag:
- test 
---

## Design Pattern by 수제비

* 디자인 패턴 
* 디자인 패턴 분류 
* 디자인 패턴 종류  
<br>

<hr>

### 디자인 패턴
<br>
　소프트웨어 개발 방법에서 사용되는 **디자인 패턴**은 프로그램 개발에서 자주 나타나는 과제를 해결하기 위한 방법 중 하나로, 과거의 소프트웨어 개발 과정에서 발견된 설계의 노하우를 축적하여 이름을 붙여, 이후에 재사용하기 좋은 형태로 특정의 규약을 묶어서 정리한 것이다. 알고리즘과 같이 프로그램 코드로 바로 변환될 수 있는 형태는 아니지만, 특정한 상황에서 구조적인 문제를 해결하는 방식이다.

　즉, 소프트웨어를 설계할 때 또는 프로그램 개발 과정에서 `특정 부분에서 많이 발생하는 문제를 정리`하여 상황에 따라 해결할 수 있는 해결책 (패턴)이다.

<br>

### 디자인 패턴 분류
<br>
① **생성 패턴(Creational Pattern)**  
　: 객체의 생성과 관련된 패턴
<p>
추상 팩토리(Abstract Factory), 빌더(Builder), 팩토리 메소드(Factory Method), 프로토타입(Prototype), 싱글톤(Singleton)
</p>
{: .notice}

② **구조 패턴(Structural Pattern)**  
　: 클래스나 객체들을 조합하여 더 큰 구조로 만들 수 있게 해주는 패턴
<p>
어댑터(Adapter), 브리지(Bridge), 컴포지트(Composite), 데코레이터(Decorator), 퍼싸드(Facade), 플라이웨이트(Flyweight), 프록시(Proxy)
</p>
{: .notice}

③ **행위 패턴(Behavioral Pattern)**  
　: 클래스나 객체들이 서로 상호작용하는 방법이나 책임 분배 방법을 정의하는 패턴
<p>
책임 연쇄(Chain of Responsibility), 커맨드(Command), 인터프리터(Interpreter), 반복자(Iterator), 중재자(Mediator), 메멘토(Memento), 옵서버(Observer), 상태(State), 전략(Strategy), 템플릿 메소드(Template Method), 방문자(Visitor)
</p>
{: .notice}

<br>

### 디자인 패턴 종류
<br>
ㆁ **Abstract Factory**  
　구체적인 클래스에 의존하지 않고 서로 연관되거나 의존적인 객체들의 조합을 만드는 인터페이스를 제공하는 디자인 패턴

ㆁ **Factroy Method**  
　객체 생성 처리를 서브(하위) 클래스로 분리해 처리하도록 캡슐화하는 패턴

ㆁ **Singleton**  
　전역 변수를 사용하지 않고 객체를 하나만 생성하도록 하며, 생성된 객체를 어디에서든지 참조할 수 있도록 하는 패턴

ㆁ **Builder**  
　복잡한 인스턴스를 조립하여 만드는 구조로, 복합 객체를 생성할 때 객체를 생성하는 방법(과정)과 객체를 구현(표현)하는 방법을 분리함으로써 동일한 생성 절차에서 서로 다른 표현 결과를 만들 수 있는 디자인 패턴

ㆁ **Bridge**  
　기능의 클래스 계층과 구현의 클래스 계층을 연결하고, 구현부에서 추상 계층을 분리하여 추상화된 부분과 실제 구현 부분을 독립적으로 확장할 수 있는 디자인 패턴

ㆁ **Adapter**  
　기존 생성된 클래스를 재사용할 수 있도록 중간에서 맞춰주는 역할을 하는 인터페이스를 만드는 패턴으로, 상속을 이용하여 클래스 패턴과 위임을 이용하는 인스턴스 패턴의 두가지 형태로 사용되는 디자인 패턴

ㆁ **Composite**  
　객체들의 관계를 트리 구조로 구성하여 부분-전체 계층을 표현하는 패턴으로, 사용자가 단일 객체와 복합 객체 모두 동일하게 다루도록 하는 디자인 패턴

ㆁ **Prototype**  
　처음부터 일반적인 원형을 만들어 놓고, 그것을 복사한 후 필요한 부분만 수정하여 사용하는 패턴으로, 생성할 객체의 원형을 제공하는 인스턴스에서 생성할 객체들의 타입이 결정되도록 설정하며 객체를 생성할 때 갖추어야 할 기본 형태가 있을 때 사용되는 패턴

ㆁ **Decorator**  
　객체의 결합을 통해 기능을 동적으로 유연하게 확장할 수 있게 해주는 패턴

ㆁ **Observer**  
　한 객체의 상태 변화에 따라 다른 객체의 상태도 연동되도록 일대다 객체 의존 관계를 구성하는 패턴

ㆁ **Iterator**  
　컬렉션 구현 방법을 노출시키지 않으면서도 그 집합체 안에 들어있는 모든 항목에 접근할 수 있는 방법을 제공하는 디자인 패턴

ㆁ **State**  
　객체의 상태에 따라 객체의 행위 내용을 변경해주는 디자인 패턴

ㆁ **Strategy**  
　행위를 클래스로 캡슐화해 동적으로 행위를 자유롭게 바꿀 수 있게 해주는 디자인 패턴

ㆁ **Template Method**  
　어떤 작업을 처리하는 일부분을 서브 클래스로 캡슐화해 전체 일을 수행하는 구조는 바꾸지 않으면서 특정 단계에서 수행하는 내역을 바꾸는 디자인 패턴

ㆁ **Command**  
　실행될 기능을 캡슐화함으로써 주어진 여러 기능을 실행할 수 있는 재사용성이 높은 클래스를 설계하는 디자인 패턴

ㆁ **Visitor**  
　각 클래스 데이터 구조로부터 처리 기능을 분리하여 별도의 클래스를 만들어놓고 해당 클래스의 메서드가 각 클래스를 돌아다니며 특정 작업을 수행하도록 만드는 패턴으로, 객체의 구조는 변경하지 않으면서 기능만 따로 추가하거나 확장할 때 사용하는 디자인 패턴

ㆁ **Mediator**  
　객체지향설계에서 객체의 수가 너무 많아지면 서로 통신하느라 복잡해져 객체지향에서 가장 중요한 느슨한 결합의 특성을 해칠 수 있다. 이를 해결하는 한가지 방법으로 중간에 이를 통제하고 지시할 수 있는 역할을 하는 중재자를 두고, 중재자에게 모든 것을 요구하여 통신의 빈도수를 줄여 객체지향의 목표를 달성하게 해주는 디자인 패턴

ㆁ **Memento**  
　객체를 이전 상태로 복구시켜야하는 경우, '작업취소(undo)'를 요청하는 디자인 패턴

ㆁ **Interpreter**  
　언어의 다양한 해석, 구체적으로 구문을 나누고 그 분리된 구문의 해석을 맡는 클래스를 각각 작성하여 여러 형태의 언어 구문을 해석할 수 있게 만드는 디자인 패턴 (문법 자체를 캡슐화)

ㆁ **Facade**  
　복잡한 시스템에 대하여 단순한 인터페이스를 제공함으로써 사용자와 시스템 간, 또는 여타 시스템과의 결합도를 낮추어 시스템 구조에 대한 파악을 쉽게 하는 패턴이다. 오류에 대해서 단위별로 확인할 수 있게 하며, 사용자의 측면에서 단순한 인터페이스를 제공하여 접근성을 높일 수 있는 디자인 패턴

ㆁ **Chain of Responsibility**  
　정적으로 어떤 기능에 대한 처리의 연결이 하드코딩되어 있을 시, 기능 처리의 연결 변경이 불가능한테 이를 동적으로 연결되어 있는 경우에 따라서 다르게 처리될 수 있도록 연결한 디자인 패턴

ㆁ **Proxy**  
　'실체 객체에 대한 대리 객체' 로 실체 객체에 대한 접근 이전에 필요한 행동을 취할 수 있게 만들며, 이 점을 이용해 미리 할당하지 않아도 상관없는 것들을 실제 이용할 때 할당하게 하여 메모리 용량을 아낄 수 있으며, 실체 객체를 드러나지 않게 하여 정보은닉의 역할도 수행하는 디자인 패턴

ㆁ **Flyweight**  
　다수의 객체로 생성될 경우 모두가 갖는 본질적인 요소를 클래스화하여 공유함으로써 메모리를 절약하고, '클래스의 경량화'를 목적으로 하는 디자인 패턴

<br>

#### REFERENCE
https://helloworld-88.tistory.com/291 <br>
https://www.notion.so/23-1959a781210b48b0b726cba983231649 
{: .notice}