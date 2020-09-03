---
layout: post
title:  "Android Layout"
categories:
  - Android
tag:
- android 
- java
- kotlin
---

<br>

## 안드로이드 레이아웃

　안드로이드 UI 프로그램에서 화면 구성을 위한 뷰 클래스도 중요하지만, 해당 뷰들을 화면에 어떻게 배치할 것인가도 중요하다. 뷰를 적절하게 배치하는 데 사용하는 레이아웃 클래스를 살펴보자. 레이아웃 클래스는 화면에 출력되는 대상이지만, 자체 UI는 갖지 않는다. 레이아웃 클래스는 Button 같은 뷰들을 자신에게 포함(Add)하고 적절하게 배치해 화면에 한꺼번에 출력한다.

　레이아웃 클래스마다 포함된 뷰의 정렬 규칙이 다른 것이지, 특정 화면을 특정 레이아웃으로만 구성할 수 있는 건 아니다. 화면을 작성할 때 무조건 특정 레이아웃을 사용해야 완성할 수 있는 경우도 있지만, 대부분 개발자의 선택에 따른다.

<br>

## 레이아웃 종류

* LinearLayout
* RelativeLayout
* FrameLayout
* TableLayout
* GridLayout
* ConstraintLayout

<br>

### 📱 LinearLayout
<br>
　가장 많이 이용되는 레이아웃 중 하나가 LinearLayout 이다. 이는 해당 레이아웃에 포함된 뷰를 순서대로 가로나 세로 방향으로 나열한다. 따라서 다른 레이아웃에서는 없는 방향을 지정하는 orientation 속성을 제공한다.

  > 기본적으로 레이아웃에서 뷰의 위치는 왼쪽 위이다. 뷰의 정렬과 관련된 속성은 **gravity**(뷰의 내용을 뷰 영역 내 어디에 나타낼지)와 **layout_gravity**(뷰를 LinearLayout 영역 내 어디에 나타낼지)로 다룰 수 있다.

  > **weigh** 속성은 이용 빈도가 높은 속성이다. 여백과 관련이 있는 속성으로, 레이아웃에 뷰를 배치하다 보면 가로나 세로 방향으로 여백이 발생할 수 있다. 이 여백을 화면에 배치된 뷰들이 확장해서 차지하게 할 때 이용된다.

<br>

### 📲 RelativeLayout
<br>
　RelativeLayout은 화면에 이미 배치된 뷰를 기준으로 다른 뷰의 위치를 지정하는 레이아웃이다. 예를 들어, RelativeLayout에 Button을 포함한 후 다른 Button을 포함하면, 이전 Button 위에 덮어쓰듯이 올라가게 된다. 이때 가로세로 방향의 orientation을 생각할 수 있는데, orientation 속성은 LinearLayout에만 지정할 수 있다. RelativeLatout에서 **상대 위치를 지정하는 속성**은 다음 4가지가 있다. 이 4가지 속성값은 `기준 뷰의 id`이다.

 > android:layout_above: 기준 뷰의 윗부분에 배치 <br> android:layout_below: 기준 뷰의 아랫부분에 배치 <br> android: layout_toLeftOf: 기준 뷰의 왼쪽에 배치 <br> android: layout_toRightOf: 기준 뷰의 오른쪽에 배치

　위와 같은 속성뿐 아니라, 기준이 되는 뷰와 왼쪽 변을 맞추거나 윗변을 맞추는 등의 작업도 중요하다. 이 부분을 지원하기 위한 속성이 align이다.

 > android:layout_alignTop: 기준 뷰와 윗부분을 정렬 <br> android:layout_alignBottom: 기준 뷰와 아랫부분을 정렬 <br> android:layout_alignLeft: 기준 뷰와 왼쪽을 정렬 <br> android:layout_alignRight: 기준 뷰와 오른쪽을 정렬 <br> android:layout_alignBaseline: 기준 뷰와 텍스트 기준선을 정렬

<br>

### 📳 FrameLayout
<br>
　FrameLayout은 레이아웃에 포함된 뷰들을 같은 영역에 겹쳐서 배치할 때 사용한다. 레이아웃 자체의 특별한 속성은 없다. 이를 이용하는 목적은 대부분 같은 영역에 여러 뷰를 겹치게 한 다음, 한 순간에 하나의 뷰만 보이기 위함이다. 이를 위해 visibility 속성으로 특정 순간에 뷰가 보이거나 보이지 않게 제어하면 된다.

 TabHost: 탭 화면은 화면 여러 개를 준비한 다음, 사용자가 버튼을 누를 때 버튼과 연결된 화면을 하나씩 보여주는 형태로 TabHost 클래스를 사용해 작업을 더 쉽게 할 수 있다.
 {: .notice_info}

<br>

### 📴 TableLayout
<br>
　TableLayout은 뷰를 테이블 구조로 나열하는 레이아웃이다. 레이아웃 내에 하나의 뷰가 여러 셀을 차지하게 할 수도 있으며, 여백이 발생할 경우 특정 열(column)을 확장할 수도 있고, 화면 크기를 벗어나는 순간 특정 열을 축소하는 등 다양하게 설정할 수 있다.

<br>

### 📱 GridLayout
<br>
　GridLayout은 뷰를 테이블 구조로 나열한다. 이는 뷰가 테이블 구조로 나열된다는 점에서 TableLayout과 유사하고, 뷰가 레이아웃에 포함된 순서대로 가로나 세로 방향으로 나열된다는 점에서 LinearLayout과도 유사하다. 또한, LinearLayout에는 없는 자동 개행 능력도 있어 화면에는 TableLayout처럼 보이기도 한다.

 > TableLayout이 있는데, GridLayout을 사용하는 이유? <br> TableLayout은 각 행을 TalbeRow로 묶어주어야 하므로, 셀의 개수를 예상할 수 없거나 가변적일 때는 화면 구성이 복잡해진다. 하지만 GridLayout은 별도로 행을 표현하지 않아도 뷰를 순서대로 포함만 하면 알아서 개행하여 행이 자동으로 표현되므로 편리한 측면이 있다.

 > orientation: 뷰의 배치 방향을 지정. 기본값은 가로 방향 <br> columnCount: 가로 방향일 때 한 줄에 몇 개의 뷰를 나열할 것인지 지정 <br> rowCount: 세로 방향일 떄 한 줄에 몇 개의 뷰를 나열할 것인지 지정

<br>

### 📲 ConstraintLayout
<br>
　ConstraintLayout은 안드로이드 2.3 버전부터는 XML 파일을 만들면 기본으로 지정되는 레이아웃이다. 이는 RelativeLayout과 상당히 유사하다.

 > 상대적 위치 지정: app: layout_constraintLeft_toRightOf <br> 여백(margin): android:layout_marginStart <br> 가운데 맞춤과 치우침(bias): app: layout_constraintHorizontal_bias <br> 비율(ratio): app: layout_constraintDimensionRatio

<br>

#### REFERENCE
깡쌤의 안드로이드 프로그래밍, 루비페이퍼 <br>
RelativeLayout: https://recipes4dev.tistory.com/126
{: .notice}