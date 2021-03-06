---
layout: post
title:  "[BoostCourse] Android Programming 04"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## 화면 내비게이션
#### by boostcourse

* 프래그먼트 이해하기
* 프래그먼트 사용하기
* 액션바 사용하기
* 탭 만들기
* 뷰페이저 사용하기
* 바로가기 메뉴 만들기

<br>

### 🔑 프래그먼트 이해하기
<br>
　안드로이드에서 화면은 액티비티로 만들어진다. 화면 제작 중에 부분 화면을 제작해야 하는 상황이 발생할 수 있다. 부분 화면을 액티비티(뷰)로 반복해 만들어 간다면, 코드를 지속적으로 새로 작성해야 하는 불편함뿐만 아니라 액티비티를 관리하는 시스템에 부담이 커진다. 시스템이 액티비티를 관리하는 것처럼 부분 화면을 독립적으로 제작하는 방식을 통해 만들어진 것이 '프래그먼트' 이다. 프래그먼트는 **액티비티가 시스템의 역할**을 대신하기 때문에, 액티비티보다 가볍게 화면을 전환할 수 있다. 
<br>
　액티비티의 수명 주기에서 onAttach와 onDetach가 추가된다. onAttach는 onCreate보다 먼저 호출되면 프래그먼트가 액티비티 위에 올라감을 의미한다. 

<p>
**MainActivity.java** <br>
MainFragment fragment = new MainFragment(); <br>
getSupportFragmentManager().beginTransaction().add(R.id.container, fragment).commit(); <br>
<br>
**MainFragment.java** <br>
ViewGroup rootView = (ViewGroup) inflater.inflate(R.layout.fragment_main, container, false); <br>
return rootView; <br>
</p>
{: .notice}


  > R.id.container 는 프래그먼트를 담을 공간 <br> add 대신 replace 메소드 사용 시 기존 프래그먼트를 대체함

<br>

### 🪓 프래그먼트 사용하기
<br>
　액티비티와 프래그먼트는 메소드와 인터페이스를 사용하여 소통할 수 있다. 프래그먼트는 인터페이스가 구현된 상위 액티비티의 메소드로 데이터를 전달하고, 액티비티는 인스턴스로 가지고 있는 프래그먼트의 메소드로 데이터를 전달할 수 있다. 즉 프래그먼트에서 액티비티로 데이터를 전달할 때에는 인터페이스가 필요하지만, 액티비티에서 프래그먼트로 데이터를 전달할 때는 단순한 메소드 호출로 가능하다.

<br>

### 🔨 액션바 사용하기
<br>
　액션바는 상단 타이틀을 말하며, 현재는 툴바의 기능 또한 가지고 있다.
<br>
　메뉴는 옵션 메뉴(액션바에 통합됨)와 컨텍스트 메뉴(팝업)으로 나뉜다. onCreateOptionsMenu 를 통해 옵션 메뉴를 생성할 수 있으며, getMenuInflater.inflate() 를 이용해 인플레이션 작업을 해야 한다. onOptionsItemSelected는 옵션 메뉴 아이템을 클릭했을 때 호출하는 메서드이다. 메서드 내부에서 item.getItemId()를 사용해 아이템을 선택할 수 있다. 

<p>
**menu 태그 내부** <br>
<item id, title, icon, app:showAsAction, app:actionLayout> <br>
showAsAction = "always" "ifRoom" "withText" "never" <br>
actionLayout = "@layout/search_layout" //이런식으로 부분화면 레이아웃 추가가능 <br>
</p>
{: .notice}

<br>

### ⛏ 탭 사용하기
<br>
　탭은 하나의 화면에 여러 가지 서브화면들을 넣어둘 수 있는 장점이 있어 자주 사용된다. 몇 개의 탭 버튼이 상단이나 하단에 있고 그 탭 버튼을 누르면 화면이 전환되는 방식이다.
<br>
　CoordinatorLayout을 사용하면 상단에 액션바 추가 시에 액션바와 아래 화면이 겹치지 않도록 생성해줄 수 있다. 강의는 해당 레이아웃 내에 액션바와 하단 탭 버튼을 추가하는 예제를 진행한다.

<p>
CoordinatorLayout-AppBarLayout-Toolbar-/AppBarLayout-TabLayout/-/Coor-> FrameLayout <br>
app:layout_behavior="@string/appbar_scrolling_view_behavior" //FrameLayout이 원래 레이아웃 화면 부분이며, 상단은 액션바 영역임을 구분함 <br>
</p>
{: .notice}

<br>

### ⚒ 뷰페이저 사용하기
<br>
　뷰페이저란 좌우 스크롤을 통해 하나의 뷰페이저 안에 들어가있는 화면이 넘어가는 기능을 제공한다. 일반적으로 뷰페이지 안에 여러 개의 부분 화면인 프래그먼트가 들어간다. 여러 개의 아이템 중 하나를 선택하는 '선택 위젯'이므로 어댑터를 사용한다. 즉 어댑터가 실제 데이터를 관리하고 뷰페이저는 껍데기를 역할을 하게 된다.
<br>
　뷰페이저의 화면이 몇개이고, 몇번째 화면인지 알고 싶을 때는 타이틀스트립(PagerTitleStrip) 혹은 탭스트립(PagerTapStrip)을 사용한다. 예시로 타이틀스트립을 사용하는 경우에는, 프래그먼트 어댑터 내에 getPageTitle 메서드를 통해 페이지마다 타이틀을 붙여 리턴하면 된다.

<p>
MainActivity extends FragmentStatePagerAdapter <br>
ArrayList Fragment items // 프래그먼트 아이템 관리 <br>
viewpager.setOffscreenPageLimit(3) // 몇 개의 화면을 보여줄지 <br>
viewpager.setAdapter(adpater); <br>
</p>
{: .notice}

<br>

### 🛠 바로가기 메뉴 만들기
<br>
　타이틀 왼쪽에 햄버거 모양의 아이콘을 바로가기 메뉴 화면이라고 부른다. 안드로이드에서는 NavigationDrawer라고 불리며 이는 기본적으로 제공된다. 해당 기능은 프래그먼트로 구성되기 때문에 프래그먼트의 동작원리를 정확히 이해하는 것이 중요하다. 

<br>

#### REFERENCE
boostcourse 안드로이드 앱 프로그래밍, 4. 화면 내비게이션 <br>
https://www.boostcourse.org/mo316/joinLectures/13161
{: .notice}