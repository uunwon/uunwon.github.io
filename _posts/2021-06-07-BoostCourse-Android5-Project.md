---
layout: post
title:  "[BoostCourse] Android 5th Project"
categories:
  - Android
  - BoostCourse
tag:
- android 
- java
- kotlin
---

## Project-E note
#### by boostcourse

<br> API를 통해 서버에서 데이터를 조회한 후 화면에 표시하도록 합니다.  
http://boostcourse-appapi.connect.or.kr:10000/  

### 🌟 과제 요구사항

* 제공되는 영화API를 보고 서버에 요청하고 응답받는 방법을 파악  
* 서버에 영화목록 데이터를 요청하고 응답을 받아 영화목록 화면에 표시  
* 서버에 영화상세 데이터를 요청하고 응답을 받아 영화상세 화면에 표시  
* 서버에 한줄평 데이터를 요청하고 응답을 받아 한줄평 리스트가 보이는 부분에 표시  
* 사용자가 한줄평을 작성했을 때 해당 데이터를 서버에 보내어 저장
* 서버에 올라가 있는 영화 이미지를 가져와 화면에 보여주기

<br>

+ Glide와 Universal Image Loader 라이브러리 사용 가능
+ Volley 라이브러리를 이용해 영화API 서버에 요청하고 응답받기
+ 응답으로 받은 JSON 문자열을 Gson으로 자바 객체화하기
+ 인터넷 접근 권한 설정

### ⭐ 과제 수행

<br>

#### REFERENCE
APM 이란?  
https://velog.io/@jiyoonoh-dev/APM%EC%9D%B4%EB%9E%80  
{: .notice}