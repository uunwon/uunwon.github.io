---
layout: post
title:  "[BoostCourse] Android Programming 02"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## 이벤트와 리스트뷰
#### by boostcourse

* 스크롤뷰 사용하기
* 이벤트 이해하기
* 토스트와 대화상자
* 비트맵 버튼 만들기
* 인플레이션 이해하기
* 리스트뷰 만들기

<br>

### 🔑 스크롤뷰 사용하기
<br>
　스크롤뷰는 말그대로 스크롤 기능을 위해 사용한다. 글자가 이지미가 들어간 뷰가 화면 영역을 벗어나면 보이지 않는 경우에 대비할 수 있다. 해당 뷰는 원하는 영역을 ScrollView 태그로 감싸면 된다.

<br>

### 🪓 이벤트 이해하기
<br>
　화면을 터치했을 때는 '이벤트'가 발생한다. 해당 이벤트는 화면의 어느 부분에 어떻게 클릭하거나 터치했는지에 대한 정보를 담았으며, 리스너를 이용해 다룰 수 있다. (ex. OnClickListenr 인터페이스) 예시로, 버튼에 리스너를 등록해두면 버튼이 클릭될 때마다 리스너의 메소드가 자동으로 호출되게 된다. 그 외에도 터치 이벤트와 키 이벤트가 있다.

　`터치 이벤트`
 > boolean onTouchEvent (MotionEvent event)

　`키 이벤트`
 > boolean onKeyDown (int keyCode, KeyEvent event) <br> boolean onKeyUp (int keyCode, KeyEvent event) <br> void onBackPressed() // keyCode == KeyEvent.KEYCODE_BACK

<br>

### 🔨 토스트와 대화상자
<br>
　**토스트(Toast)** 는 간단한 메시지를 화면에 띄어주는 역할을 한다. Log 클래스를 이용해 콘솔에 메시지를 출력할 수도 있지만, 화면에 보여주고 싶다면 토스트 기능을 사용한다.

　유사한 역할로, **스낵바**는 화면 내 아래쪽에서 올라왔다가 사라지는 뷰이다.

<p>
Toast.makeText(Context context, String message, int duration).show(); <br>
Snackbar.make(View view, CharSequence text, int duration).show();
</p>
{: .notice}

　사용자에게 어떤 내용을 알려주거나 '예', '아니오' 버튼을 선택하도록 할 때는 **알림 대화상자(AlertDialog)**를 사용한다. 이는 AlertDialog.Builder 객체를 사용하여, AlertDialog 객체를 만들어 show 메소드를 이용해 화면에 표시한다.

<p>
AlertDialog.Builder builder = new AlertDialog.Builder(this); <br>
AlertDialog dialog = builder.create(); <br>
dialog.show();
</p>
{: .notice}

<br>

### ⛏ 비트맵 버튼 만들기
<br>
　**① 나인패치(9Patch)**  
　이미지 파일 이름에 .9 라는 글자를 붙여 나인패치 이미지를 생성할 수 있다. 이는 이미지의 깨질 가능성이 있는 부분은 늘리지 않아, 이미지의 크기가 변형되더라도 덜 왜곡된다.

　**② 비트맵 버튼(BitmapButton)**  
　Button 을 상속하여 새로운 비트맵 버튼을 생성할 수 있다. 나인패치 이미지를 적용하는 대표적인 경우가 버튼인데, 배경을 이미지로 지정하여 만든 버튼은 눌러도 이미지의 변화가 없다. 이같은 단점을 보완하기 위해 비트맵 이미지를 이용해 버튼의 상태를 이벤트로 구분해 표시할 수 있다. 배경 이미지가 변경되면 `invalidate 메소드를 사용해 화면을 갱신`해야 한다.

<br>

### ⚒ 인플레이션 이해하기
<br>
　XML 레이아웃에 정의된 내용이 실제 메모리에 객체화되는 (생성되는) 과정을 **인플레이션 과정**이라 한다. 이같은 레이아웃 인플레이션 과정은 setContentView() 메소드를 통해 (XML 파일의 전체 화면을) 할 수 있다. 부분 화면의 경우에는 LayoutInflater 를 이용해서 직접 메모리에 객체화를 해야 한다. 인플레이션 후에는 아이디를 통해서 내부의 뷰를 찾아 사용할 수 있다!

<p>
FrameLayout container = findViewById(R.id.container); <br>
LayoutInflater inflater = (LayoutInflater) getSystemService(Context.LAYOUT_INFLATER_SERVICE); <br>
inflater.inflate(R.layout.보여줄_XML_파일명, container, true);
</p>
{: .notice}

<br>

### 🛠 리스트뷰 만들기
<br>
　리스트뷰에는 여러 개의 데이터를 넣어 보여줄 수 있는데, 좀 더 쉽게 만들 수 있도록 어댑터를 만들어 사용한다. 어댑터는 여러 개의 아이템 중에서 하나를 선택하는 방식을 가진 선택 위젯에서 사용된다. 뷰가 데이터를 관리하는 것이 아닌, 어댑터가 실제 데이터를 관리하는 것이다. 각각의 아이템을 위한 뷰도 어댑터에서 만들어주기 때문에 리스트뷰는 어댑터의 getView 메소드를 호출해 뷰 객체를 반환받은 뒤 화면에 보여주게 된다.

　최근 실무에서는 리스트뷰(ListView)보다 리사이클러뷰(RecyclerView)를 더 많이 사용한다.

 > 유사한 선택 위젯으로 스피너와 그리드뷰가 있다.

<br>

#### DETAIL
@Override : 이미 구현되어있는 코드를 덮어쓴다는 의미로, 해당 의미를 컴퓨터에게 알려주는 용도다.

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 2. 이벤트와 리스트뷰 <br>
https://www.boostcourse.org/mo316/joinLectures/13159 <br> <br>
Bitmap Button 만들기 <br>
https://qlyh8.tistory.com/44
{: .notice}