---
layout: post
title:  "[BoostCourse] Android Programming 03"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## 화면 여러 개 만들기
#### by boostcourse

* 화면 전환하기
* 인텐트 살펴보기
* 수명주기 이해하기
* 서비스 사용하기
* 브로드캐스트 수신자 사용하기

<br>

### 🔑 화면 전환하기
<br>
　시스템이 관리하는 애플리케이션 구성요소는 액티비티(Acitity)ㆍ서비스(Service)ㆍ브로드캐스트 리시버(Broadcast Receiver)ㆍ내용 제공자(Content Provider) 가 있다. 각 클래스들은 안드로이드 SDK가 제공하며, 매니페스트 파일을 통해 어떤 애플리케이션 구성요소가 포함되어 있는 지 확인할 수 있다. 

　애플리케이션 구성요소 중 **액티비티(Activity)**는 안드로이드 앱에서 하나의 화면을 만든다. 하나의 액티비티가 또 다른 액티비티로, 즉 화면이 전환되기 위해 **인텐트(Intent)** 객체를 사용한다. startActivityForResult 메소드를 호출하면 인텐트 객체가 시스템(액티비티 매니저)으로 전달된다. 액티비티 매니저는 인텐트가 지정한 액티비티를 실행하여 화면에 보여주게 된다.

<p>
// 클래스 인스턴트를 인텐트의 파라미터로 넘겨주는 방식 <br>
Intent intent = new Intent(Context pakageContext, Class<?> cls); <br>
startActivityForResult(intent, INT_REQUEST_CODE); <br>
<br>
startActivityForResult(new Intent(MainActivity.this, SubActivity.class), INT_REQUEST_CODE); <br>
<br>
// ComponentName 객체 만들어 설정하는 방식 <br>
Intent intent = new Intent(); <br>
ComponentName name = new ComponentName("org.techtown.intent", "org.techdown.intent.SubActivity"); <br>
intent.setComponent(name); <br>
startActivityForResult(intent, INT_REQUEST_CODE); <br> <br>
finish();
</p>
{: .notice}

<br>

### 🪓 인텐트 살펴보기

#### 인텐트 종류
　시스템에서 이해할 수 있는 객체로 만들어진 것이 **인텐트(Intent)**이며, 화면을 실행할 때 인텐트가 사용된다. 인텐트에는 컴포넌트 A가 컴포넌트 B를 호출할 때 필요한 정보를 담고 있으며, 이 정보에는 호출되는 컴포넌트 B의 이름이 `명시적`으로 표시되기도 하고, 속성들이 `암시적`으로 표시되기도 한다.

 > ① 명시적 인텐트 <br> 인텐트에 클래스 객체 컴포넌트 이름을 지정하여 호출된 대상을 확실히 알 수 있는 경우에 사용한다. 주로 애플리케이션 내부에서 사용한다.

 > ② 암시적 인텐트 <br> 인텐트의 액션과 테이터를 지정하긴 했지만, 호출할 대상이 달라질 수 있는 경우에는 암시적 인텐트를 사용한다. 즉, 설치된 애플리케이션들에 대한 정보를 알고 있는 안드로이드 시스템이 인텐트를 이용해 요청한 정보를 처리할 수 있는 적절한 컴포넌트를 찾아본 다음, 사용자에게 그 대상과 처리 결과를 보여주는 과정을 거치게 된다.

<br>

#### 인텐트 플래그
 　새로 실행하려는 액티비티와 화면에 보이는 액티비티가 동일한 액티비티인 경우 (ex. 서비스), 플래그를 사용하여 메모리에 액티비티를 새로 만들지 않고 화면에 보이는 액티비티를 재사용한다. 이같은 경우에 onCreate 메소드 대신 onNewIntent 메소드가 호출되어 인텐트를 전달받을 수 있다. 액티비티를 재사용할 시에는 인텐트에 추가할 수 있는 옵션인 **플래그**를 활용한다. 즉, 시스템이 인텐트를 해석한 후 동작시킬 때 옵션에 따라 다른 동작을 하도록 한다. 플래그를 이해하기 위해서는 액티비티 스택에서 액티비티가 관리된다는 점을 알아야 한다.

 <p>
 intent.setFlags(Intent.FLAG_ACTIVITY_SINGLE_TOP); //설정 <br>
 intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP); //추가
 </p>
 {: .notice}

 <br>

#### 부가 데이터

★★★★★★★★★★★★★★ <br>
작성 必 <br>
★★★★★★★★★★★★★★

<br>

### 🔨 수명주기 이해하기

★★★★★★★★★★★★★★ <br>
작성 必 <br>
★★★★★★★★★★★★★★

<br>

### ⛏ 서비스 사용하기

★★★★★★★★★★★★★★ <br>
작성 必 <br>
★★★★★★★★★★★★★★

<br>

### ⚒ 브로드캐스트 수신자 사용하기

★★★★★★★★★★★★★★ <br>
작성 必 <br>
★★★★★★★★★★★★★★

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 3. 화면 여러 개 만들기 <br>
https://www.boostcourse.org/mo316/joinLectures/13160 <br>
[Android] Intent <br>
https://woovictory.github.io/2019/01/02/Android-What-is-Intent/ <br>
Intent의 Flag 사용법 <br>
https://ju-hy.tistory.com/46
{: .notice}