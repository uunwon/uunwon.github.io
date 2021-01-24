---
layout: post
title:  "[BoostCourse] Android Programming 06"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## 데이터베이스
#### by boostcourse

* 데이터베이스 이해하기
* 데이터베이스와 테이블
* 데이터 추가하고 조회
* 헬퍼 사용하기
* 연결상태 확인하기

<br>

### 🔑 데이터베이스 이해하기
<br>
　★★ 01 / 08 포스트 ★★

<br>

### 🪓 소켓 사용하기
<br>
　네트워킹이란, 클라이언트(요청)와 서버(응답)의 동작 방식을 말한다. 안드로이드에서는 네트워킹을 사용할 때 반드시 스레드를 사용하며, **post 메소드** 사용을 권장한다. 

　소켓은 서버 소켓과 클라이언트 소켓을 만들고 서로 연결하는 과정을 갖는다. 서버 소켓은 연결을 기다리는 역할, 클라이언트 소켓은 연결을 만드는 역할을 한다. 서버는 ServerSocket 클래스를 이용해 객체를 만들고 accept 함수를 호출하여 클라이언트로부터의 접속을 기다린다. 클라이언트는 IP와 서버와 동일한 포트 번호를 전달하고, 서버에 접속한다.

　데이터를 보내고 받는 방식으로는 ObjectOutputStream(데이터 전송)의 writeObject 메소드와 ObjectInputStream(데이터 수신)의 readObject 메소드를 사용한다. 데이터를 전송한 후에는 **flush** 메소드를 이용해 현재 버퍼에 저장되어 있는 내용을 클라이언트로 전송하고, 버퍼를 비운다.

<br>

### 🔨 웹으로 요청하기
<br>
　소켓은 두개의 컴퓨터 간에 통로를 만들어주고 통로 간에 데이터를 주고받을 수 있게 만들어주는 방법이다. 최근엔 소켓보다 웹이 많이 사용되는데, 웹서버는 **HTTP 요청**을 받아 처리할 수 있다. 데이터를 주고받는 HTTP 포맷은 어떤 것들이 들어갈 수 있는 지 표준으로 정해진 **헤더(Header)**와 데이터가 들어간 **바디(Body)**로 구성된다.

　앱에서 웹서버에 요청하는 방식은 기존의 표준 자바와 다르지 않지만, 스레드를 사용한다는 점을 염두해야 한다. 가장 기본적인 방법으로 HttpURLConnection 객체를 사용하여 작성해볼 수 있다. 해당 객체에 속성을 설정하고 getResponseCode 메소드를 호출하면 웹서버에 연결하고 응답을 받아준다. 응답 데이터를 화면에 표시할 때는 Request 메소드를 이용하면 된다.

　데이터를 읽어들일 때, BufferedReader 객체를 사용하면 한 줄씩 읽을 수 있다. 또한 웹서버에 요청하는 것이므로 인터넷 권한을 주어야 한다.

<br>

### ⛏ Volley 사용하기
<br>
　웹서버에 요청할 때 일반적으로 사용하는 HttpURLConnection 은 코드 양이 방대하다. 이를 간결화하기 위해 우리는 외부 라이브러리 **Volley**를 사용한다. Volley는 코드 양이 간결화될 뿐만 아니라, 스레드를 신경쓰지 않아도 된다는 장점이 있다.

 > 네트워크 요청 우선 순위를 자동으로 관리한다. <br> 동시에 여러 네트워크 요청을 할 수 있다. <br> 요청을 할 때 Cache 적용 여부를 의식하지 않아도 된다.

　RequestQueue를 만들고, 그 안에 Request 객체를 만들어 넣어주면 요청은 자동으로 보내지게 된다. Request 객체는 네 개의 파라미터를 전달함으로써 생성된다. 요청 방식을 지정하고, 웹서버의 URL 정보를 전달하고, 응답이 성공적일 때 호출되는 onRequest 메소드를 작성하고, 에러가 발생했을 때 호출될 리스너 객체를 작성한다.

　요청 큐는 앱이 시작되었을 때 초기화되어 있으면 되며, 한번 만들어두면 계속 사용할 수 있다. Application 클래스를 정의하고 앱에 등록하여 사용하는 경우에는 Application 클래스 안에 넣어둘 수도 있고, 별도의 클래스를 만들어 넣어둘 수도 있다.

<p>
implementation 'com.android.volley:volley:1.1.0'
</p>
{: .notice}

<br>

### ⚒ JSON 이해하기
<br>
　★★★★★★★ <br>
　작성 必 <br>
　★★★★★★★ <br>

### 🛠 이미지 다운로드하기
<br>
　★★★★★★★ <br>
　작성 必 <br>
　★★★★★★★ <br>

### 🔧 영화API 사용하기
<br>
　★★★★★★★ <br>
　작성 必 <br>
　★★★★★★★ <br>

<br>

#### DETAIL
HTTP(Hyper Text Transfer Protocol): HTML과 같은 문서 정보를 주고받을 수 있는 프로토콜(규약, 약속)

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 5. 네트워킹 <br>
https://www.boostcourse.org/mo316/joinLectures/13169 <br>
[JAVA] flush () <br>
https://m.blog.naver.com/PostView.nhn?blogId=klh1514&logNo=120190269672&proxyReferer=https:%2F%2Fwww.google.com%2F
{: .notice}