---
layout: post
title:  "[Android] Android LifeCycle"
categories:
  - Android
tag:
- android 
- java
- kotlin
---

## 액티비티 생명주기
#### by 깡쌤의 안드로이드 프로그래밍

　안드로이드에서 화면이 아닌 액티비티 자체가 어떤 원리로 수행되는지 살펴보자. 액티비티를 실행하는 주체는 안드로이드 시스템이므로 시스템에서 액티비티 생명주기 (life cycle) 을 어떻게 관리하며, 그때 개발자 코드에서 신경 써야 하는 부분은 무엇인지 알아본다.

 <br>

## 액티비티 상태

 1. 활성 상태(activity running): 현재 액티비티가 화면을 점유하여 출력되고 있으며 사용자 이벤트 처리가 정상으로 처리되는 상태
 2. 일시 정지 상태(pause): 현재 액티비티가 일시적으로 사용이 불가능한 상태
 3. 비활성 상태(stop): 현재 액티비티가 다른 액티비티로 인해 화면이 완벽하게 가려진 상태

<br>

### 👋🏻 활성 상태

　액티비티가 사용자 화면에 보이고 있으며 포커스를 가지고 있어 사용자 이벤트에 반응할 수 있는 상태이다. 생성된 액티비티는 onCreate() -> onStart() -> onResume() 함수가 호출되면서 활성 상태가 된다. 일반적으로 setContentView() 함수를 이용해 액티비티 화면을 출력한다고 하지만, 정확하게는 setContentView() 함수가 호출되는 시점이 화면 출력 순간이 아니라, **onResume() 함수까지 실행하고, setContentView() 함수에서 출력한 내용이 화면에 나오는 구조이다.**

　따라서 onResume() 함수가 실행되기까지 setContentView() 함수를 onCreate(), onStart(), onResume() 등 어디선가 호출해 주면 화면에 잘 나온다. 반대로 onResume() 함수가 호출될 때까지 setContentView() 함수가 한 번도 호출되지 않는다면, 화면에 아무것도 나오지 않는다.
<br><br>
### 🤏🏻 일시 정지 상태

　일시 정지 상태는 액티비티가 여전히 화면에 보이지만, 포커스를 잃은 상태이다. 대표적인 예시로 다른 액티비티가 화면 전체를 가리지 않고 실행된 때이다. 다른 액티비티가 반투명하게 실행되거나 다이얼로그 스타일로 실행되어 여전히 자신이 화면에 보이지만, 포커스를 잃은 상태이다. 이때, onPause() 함수가 자동으로 호출된다.
<br><br>
### 👊🏻 비활성 상태

　비활성 상태는 다른 액티비티로 인해 화면이 완전히 가려진 상태이다. 보통 다른 액티비티로 화면이 전환되어 안 보이는 경우다. 이때는 onPause() -> onStop() 함수까지 호출된다.

　화면을 가렸던 액티비티가 뒤로가기 비활성 상태에서 뒤로가기 버튼 등으로 화면을 가렸던 액티비티가 사라지면 다시 활성 상태로 전환되는데, 이때는 onRestart() -> onStart() -> onResume() 함수가 차례로 호출된다.

<br>

## 액티비티 상태 저장

　액티비티의 상태 관리를 위해 데이터를 저장했다가 복원하는 데 사용되는 함수는 onCreate(), onRestoreInstanceState(), onSaveInstanceState() 이다. 우선 액티비티가 종료되는 상항에 대비해 액티비티의 데이터를 저장해야 한다면 **onSaveInstanceState()** 함수를 사용한다. 이는 onPause() 함수 호출 후 자동으로 호출되며, 이 함수에서 액티비티의 데이터를 저장한다.

　저장하는 방법은 매개변수로 전달되는 Bundle을 이용하면 된다. Bundle은 컴포넌트의 데이터를 저장하기 위한 일종의 Map 객체이며, 이 객체에 데이터를 key-value로 담아주면 내부적으로 파일로 저장해줌으로써 액티비티가 종료되더라도 데이터는 유실되지 않는다. 이렇게 저장한 데이터를 액티비티가 다시 시작되는 시점에 가져와서 이용할 수 있다. 이 작업에는 onCreate()와 onRestoreInstanceState() 함수를 이용한다.

<br>

#### REFERENCE
깡쌤의 안드로이드 프로그래밍, 루비페이퍼 <br>
{: .notice}