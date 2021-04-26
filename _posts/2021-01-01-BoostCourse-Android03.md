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

　인텐트는 시스템을 통해 다른 액티비티로 전달될 수 있는데 액티비티뿐만 아니라 다른 애플리케이션 구성요소로도 전달될 수 있다. 애플리케이션 구성요소들 간에 데이터를 전달하는 데 인텐트가 사용되는 것이다. 부가 데이터는 시스템에서 건드리지 않고 전달만 되며, 인텐트 안에 번들(Bundle) 객체가 들어있어 그 안에 데이터를 넣을 때는 put, 데이터를 가져올 때는 get 메소드를 사용한다.

　기존의 put, get 메소드를 이용해 인텐트에 넣을 수 있는 부가데이터의 자료형은 기본 자료형뿐이다. 다양한 객체의 정보를 전달하기 위해서는 **Serializble** 또는 **Parcelable** 객체를 만들어 전달할 수 있다.

　데이터 클래스를 별도로 생성하여 전달할 때, 안드로이드에서는 Parcelable을 구현하는 것을 추천하고 있다. Serializable은 데이터를 효율적이지 않게 일렬 데이터로 만들어 전송하는 반면 Parcelable은 데이터 타입에 맞게 가공해준다.

<br>

### 🔨 수명주기 이해하기

　액티비티 수명주기는 액티비티의 상태가 변할 때마다 안드로이드 시스템에서 각 상황에 맞는 메소드를 자동으로 호출해줌으로써, 직접 상태에 맞는 코드를 넣어 액티비티의 상태에 따라 제어할 수 있도록 해준다.

　<img src="{{ site.url }}/images/android_lifecycle.png" alt="Android_LifeCycle" height="50">

　화면이 없어질 때 데이터를 임시로 저장할 때는 **onPause()** 메소드를, 데이터를 복구할 때는 **onResume()** 메소드를 사용한다. 이때 데이터는 SharedPreferences를 이용하면 저장할 수 있다. 또는 onSaveInstanceState 메소드와 onRestoreInstanceState 메소드를 사용하는 방법이 있다.

<br>

### ⛏ 서비스 사용하기

　**서비스(Service)**는 화면이 없는 상태(백그라운드)에서 실행되는 애플리케이션의 구성요소 중 하나다. 인터넷을 통해 데이터를 주고받는 경우가 많은데 이때 대부분 서비스라는 것을 사용하게 된다. 애플리케이션 구성요소이기 때문에 프로젝트에 추가할 때 매니페스트 파일에 <Service> 태그를 사용한다. 서비스는 startService 메소드를 호출하면 시작된다.

　startService 메소드는 또한 인텐트 안에 넣어 전달한 명령이나 데이터를 처리할 수 있도록 onStartCommand() 메소드를 사용한다. 

<p>
@Override <br>
public int onStartCommand(Intent intent, int flags, int startId) { <br>
　Log.d(TAG, "onStartCommand() 호출됨"); <br>
　return super.onStartCommand(intent, flags, startId); <br>
}
</p>
{: .notice}

　화면이 없는 서비스에서 화면이 있는 액티비티를 띄울 때는 태스크(Task)를 새로 만들어서 연결해야 한다. 그와 같은 경우에 일반적으로 세 개의 플래그(FLAG_ACTIVITY_NEW_TASK, FLAG_ACTIVITY_SINGLE_TOP, FLAG_ACTIVITY_CLEAR_TOP)를 사용한다. 그러면 액티비티는 새로 만들어지지 않고 기존 액티비티를 사용하고, onNewIntent 메소드가 자동으로 호출된다.

<br>

### ⚒ 브로드캐스트 수신자 사용하기

　브로드캐스팅이란 여러 사람에게 동시에 데이터를 전달하는 것을 말한다. 안드로이드는 여러 애플리케이션 구성 요소에게 메시지를 전달하고 싶은 경우에 브로드캐스팅을 사용한다. 브로드캐스트 수신자 또한 애플리케이션 구성요소이므로 매니페스트 파일에 정보를 추가해준다. intent-filter 태그 내에는 어떤 브로드캐스팅 메시지를 받고 싶은지 지정할 수 있다. 또한 브로드캐스팅 메시지는 인텐트 객체로 만들어져 전달된다.

<p>
receiver android:name=".SmsReceiver" <br>
　intent-filter <br>
　　action android:name="android.provider.Telephony.SMS_RECEIVED" <br>
　/intent-filter <br>
/receiver
</p>
{: .notice}

<br>

#### DETAIL
`Serialization(직렬화)` : 표준 자바 인터페이스로, 객체를 저장 장치에 저장 혹은 네트워크 전송을 위해 텍스트나 이진 형식으로 변환하는 것 <br>
`Serializble(객체 직렬화)` : 객체를 바이트로 저장하는 자바의 인터페이스 <br>
`Parcelable` : 안드로이드 구성요소간 데이터 전달 시에 편의성을 위해 사용되는 인터페이스로, 사용자 정의 자료형을 전달할 때 기본형 자료들을 분리하여 보내는 것 <br>
`Reflection` : 자바 기능 중 하나로, 클래스나 인터페이스의 정보에 직접 접근할 수 있도록 하는 API <br>
`Bundle` : 여러 가지 타입의 값을 저장하는 Map 클래스이다. 예를 들면 String 값을 Bundle 클래스에 Mapping(대응, 변환)하는 것이다. 즉, Bundle 은 아무거나 포장할 수 있는 상자를 의미하고 이 상자를 이용하여 이리저리 인텐트도 오고갈 수 있고 다양한 데이터 통신에 이용할 수 있다.

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 3. 화면 여러 개 만들기 <br>
https://www.boostcourse.org/mo316/joinLectures/13160 <br>
[Android] Intent <br>
https://woovictory.github.io/2019/01/02/Android-What-is-Intent/ <br>
Intent의 Flag 사용법 <br>
https://ju-hy.tistory.com/46 <br>
Android Bundle 이란? <br>
https://www.crocus.co.kr/1560 <br>
Android Serializable vs Parcelable <br>
https://wooooooak.github.io/android/2019/09/19/Serializable-vs-Parcelable/ <br>
Parcelable 이란? <br>
https://blog.naver.com/bestowing/222014802794 <br>
Android & Java - Reflection <br>
https://two22.tistory.com/14 
{: .notice}