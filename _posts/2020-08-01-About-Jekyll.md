---
layout: post
title:  "About Jekyll"
categories:
  - Jekyll
tag:
- jekyll 
- ruby
- blog
---

<br><img src="{{ site.url }}/images/jekyll-icon.png" alt="Jekyll" height="100">

<br><br>

## About Jekyll

　개인, 프로젝트 또는 조직 사이트를 위한 간단한 블로그 인식 정적 사이트 생성기로서 Tom Preston-Werner가 루비로 작성하였으며 오픈 소스 MIT 라이센스에 따라 배포된다. 간단히 말하면, HTML, Markdown 등 `다양한 포맷의 텍스트들을 읽고 가공하여 자신의 웹 사이트에 바로 게시`할 수 있게 해주는 Rubby 언어로 만들어진 하나의 텍스트 변환 엔진이다.

<br>

### 💡 About Ruby

　스크립트 언어이자 동적 객체 지향 프로그래밍 언어

* 들여 쓰기는 구분하지 않지만, 대/소문자 구분 필수
* '#' 부호 뒤 작성된 내용은 한 줄 단위로 주석 처리
* 원시 자료형 없이 모든 것이 객체인 순수한 객체 지향 언어

<br>

### 💡 About Scripting language

　기존에 존재하는 응용 소프트웨어(애플리케이션)를 제어하는 컴퓨터 프로그래밍 언어이다. 일반적인 응용 소프트웨어에서 수정이 빈번하게 발생하는 부분은 전체를 컴파일하는 것보다, 코드를 한줄씩 읽어 바로 실행하는 인터프리터 방식이 유리하다. 스크립트 언어는 이런 부분에서 사용하기 위해 나온 것으로, 응용 소프트웨어에서 스크립트 언어에 맞는 API를 제공한다. 이는 응용 소프트웨어와 상호작용하면서 돌아간다.

<br><br>

<img src="{{ site.url }}/images/Git-Jekyll.png">

<br>

## Jekyll Blog

 　Jekyll을 사용해 우리는 웹 서버에 곧바로 게시할 수 있는, 완성된 정적 웹사이트를 만들 수 있다. 또한 Jekyll은 Github Pages의 내부 엔진이다. 즉, Jekyll을 사용하면 자신의 프로젝트 페이지나 블로그 웹사이트를 무료로 Github에 호스팅할 수 있다.

<br>

## Jekyll Directory Structure

. <br>
┡ _config.yml <br>
┡ _data <br>
　┖ members.yml <br>
┡ _drafts <br>
　┖ begin-with-the crazy-ideas.md <br>
　┖ on-simplyicity-in-technology.md <br>
┡ _includes <br>
　┖ footer.html <br>
　┖ header.html <br>
┡ _layouts <br>
　┖ default.html <br>
　┖ post.html <br>
┡ posts <br>
　┖ 2007-10-29-why-every-programmer-should-play-nethack.md <br>
　┖ 2009-04-26-barcamp-boston-4-roudup.md <br>
┡ _sass <br>
　┖ _base.scss <br>
　┖ _layout.scss <br>
┡ _site <br>
┡ .jekyll-metadata <br>
┖ index.html # can also be an 'index.md' with valid front matter
{: .notice}

| File/Directory | Description |
|:--------|:-------:|
| _config.yml   | Jekyll 블로그를 구성하기 위한 기본적인 설정 저장   |
| _drafts   | 아직 공개하지 않은 블로그 포스트 보관   |
|-------------------|
| _includes   | 페이지 단위의 공통 요소 저장   |
| _layouts   | 템플릿 저장   |
|-------------------|
| _posts   | 블로그 포스트 저장, 파일명 형식 : YEAR-MONTH-DAY-title.MARKUP   |
| _data   | 데이터 파일 저장   |
|-------------------|
| _sass   | 디자인을 위한 sass 파일 저장   |
| _site   | jekyll에 의해 빌드된 파일 저장   |
|-------------------|
| .jekyll-metadata   | jekyll이 변경된 내용만 빌드하기 위해 관리하는 파일   |
| _indext.html or index.md   | 홈페이지의 첫 페이지   |

<br>

#### REFERENCE
https://url.kr/c3zgb4 <br>
https://nachwon.github.io/jekyllblog/ <br>
https://jekyllrb.com/docs/structure/ <br>
https://dev-yakuza.github.io/ko/jekyll/directory_structure/
{: .notice}