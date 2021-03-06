---
layout: post
title:  "[BoostCourse] Android Programming 05"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## 네트워크
#### by boostcourse

* 스레드 사용하기
* 소켓 사용하기
* 웹으로 요청하기
* Volley 사용하기
* JSON 이해하기
* 이미지 다운로드하기
* 영화API 사용하기

<br>

### 🔑 스레드 사용하기
<br>
　앱 생성 시에, 리눅스 위에서 프로세스가 생성되면서 그와 동시에 앱의 기본 실행을 담당하는 메인 스레드가 생성된다. **스레드(Thread)**는 동시에 동작하기 위한 하나의 실행 단위다. 메인 스레드와 별도로 실행되고 독립적인 실행을 위해서 추가적으로 스레드를 제작할 수 있다. 하지만 추가 제작된 스레드는 UI에 직접 접근할 수 없기 때문에, **핸들러(Handler)**를 사용한다.

　핸들러는 메인 스레드 안에서 큐처럼 동작하여, 핸들러가 요청받은 것과 메인 스레드에서 동작하는 것이 순차적으로 동작하도록 한다. 핸들러는 message 객체의 sendMessage 메소드를 가지고 데이터를 보내 처리하고, 그 메시지를 핸들러가 받아 사용하면 메인 UI를 접근할 수 있다.

　핸들러를 상속받아 클래스를 사용하는 방식, 더 간결하게는 Runnable 인터페이스를 이용해 직접 한 번 실행될 객체를 정의할 수 있다. Message 객체가 아닌 post 메소드를 호출하는 방식으로! 더욱 간결하게 처리할 수 있다.

<p>
Handler.post(new Runnable() run());
</p>
{: .notice}

　핸들러를 사용하는 방식 외에도 **AsyncTask**를 상속한 클래스로 스레드를 만들고 메인 UI에 접근까지 할 수 있다. AsyncTask는 스레드로 동작하는 코드와 UI로 접근하는 코드를 메소드로 분리해 간편하다. 즉, 명확하게 어떤 기능에 대한 처리를 스레드를 쓴다고 해도 같은 클래스 안에 코드를 넣을 수 있다는 강점이 있다.

 > doInBackground(): 스레드 안에서 실행될 코드 <br> onProgressUpdate(): 중간중간 화면(UI)를 업데이트하기 위한 실행 코드 <br> onPostExecute(): 결과 값을 전달받아 실행될 코드

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
　데이터가 왔다 갔다 할 때, HTTP 포맷이 왔다 갔다 하는 것이다. 이에 더해 우리가 대상으로 하는 **데이터 포맷**이 xml 이냐, json 인지 알아보자. **JSON**은 자바스크립트 객체 포맷의 데이터를 주고 받을 때 사용할 수 있도록 만든 것이다. 파싱 과정을 통해 JSON 형식의 데이터를 사용할 수 있는데, 이는 JSON 문자열을 해석하여 자바 객체로 만드는 과정을 말한다. 이같은 파싱은 구글이 만든 Gson에 의해 이루어진다. 

　JSON 포맷을 GSON을 이용해 자바 객체로 만들어주고, 그 객체에 들어있는 데이터를 사용할 수 있게 된다. 받아온 데이터를 JSON에 맞추어 자바 객체로 만들기 위해서는 자바 클래스를 정의한다. JSON 문자열의 속성 중 값이 배열인 경우에는, 자바 클래스를 정의할 때 ArrayList 자료형을 사용한다.

<p>
Gson gson = new Gson(); <br>
MovieList movieList = gson.fromJson(response, MovieList.class);
</p>
{: .notice}

### 🛠 이미지 다운로드하기
<br>
　위에서 웹서버에 데이터를 요청하고 응답받아 처리하는 과정을 살펴보았다. 응답받을 데이터가 **이미지**파일일 경우에는, 이미지 파일에 대한 정보만 응답 데이터에 넣어두고 이미지 파일은 별도로 다운로드 받는다. 인터넷을 사용하기 위해 스레드를 생성해야 하므로 AsyncTask를 상속해 새로운 클래스를 정의한다. 클래스 내에서 이미지를 비트맵으로 받아 화면에 보여준다.

　이미지 파일의 경우에는 파일의 크기가 크기에, 이전에 사용한 비트맵 객체는 정리한다. 외부 라이브러리(ex.UniversalImageLoader)를 사용하면 자동적으로 처리가 되며, 직접 이전의 비트맵의 존재 여부를 확인한 후 삭제할 수 있다. 클래스 안에 HashMap 객체를 만들고 이미지 주소를 메모리에 만들어진 비트맵 객체와 매핑하도록 하여 처리한다.

<p>
Bitmap bitmap = null; <br>
URL url = new URL(urlStr); <br>
bitmap = BitmapFactory.decodeStream(url.openConnection().getInputStream());
</p>
{: .notice}

<br>

#### DETAIL
HTTP(Hyper Text Transfer Protocol): HTML과 같은 문서 정보를 주고받을 수 있는 규약
API 사용 시, 크롬 내 JSONView 확장프로그램을 이용해 가시성 좋게 포맷팅 가능

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 5. 네트워킹 <br>
https://www.boostcourse.org/mo316/joinLectures/13169 <br>
[JAVA] flush () <br>
https://m.blog.naver.com/PostView.nhn?blogId=klh1514&logNo=120190269672&proxyReferer=https:%2F%2Fwww.google.com%2F
{: .notice}