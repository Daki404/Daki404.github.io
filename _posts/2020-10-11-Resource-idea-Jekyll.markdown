---
layout: post
title:  "이해 못 하고 쓰고보는 Jekyll"
subtitle:   "How to manage this blog"
categories: Resource
tags: idea
comments: true
published: false
header-img: img/Resource/idea/jekyll.png
---
### <center>Jekyll - "간단한 블로그 인식 정적 사이트 생성기"</center>
## 개요
> ruby도 모르고, html과 css도 잘 모르지만 일단 대충 수정해서 써 보자!  
__블로그 파일 다운, 수정, 디버깅, 갱신 4단계면 충분하다!__


- 목차
  - [블로그 구성 파일 다운 : Git 설치 및 git clone하기](#git-설치-및-git-clone하기)
  - [에디터로 파일 수정하기 : Atom 설치 및 사용하기](#atom-설치-및-사용하기)
  - [로컬서버로 디버깅하기 : Ruby 설치 및 로컬서버로 실행하기](#ruby-설치-및-로컬서버로-실행하기)
  - [파일 업로드 : 수정 후 git push로 업데이트 하기](#git-push로-업데이트-하기)


## Git 설치 및 git clone하기
---

일단, github에 저장되어 있는 블로그 구성 파일을 가져와야 한다.  
우선 git을 설치하여야 한다. 아래 Git 이미지를 클릭하면 된다.


<a href="https://git-scm.com/" target='_blank'><img src="https://miro.medium.com/max/1200/1*BCZkmZR1_YzDZy22Vn4uUw.png" width="314" height="131"></a>  
> <center>Git : 분산형 버전 관리 시스템(VCS).</center>

<span style="color:red">Git Bash</span>를 실행시킨다. 그리고 우선적으로 사용자 정보를 등록해준다.  

    git config --global user.name Daki404   
    git config --global user.email daki403.1@gmail.com

> 사용자 정보 등록을 통해 누가 파일을 수정한지 알 수 있다.  

그리고 <span style="color:red">git clone</span>을 통해 블로그 구성 파일들을 desktop으로 다운한다.  

    git clone https://github.com/Daki404/Daki404.github.io.git

> github에서 초록색 Code 버튼을 누르면 clone 링크가 나온다.

<center><strong>블로그 구성 파일 다운로드 완료!</strong></center><br>


## Atom 설치 및 사용하기
---

이제 다운 된 블로그 파일들을 꾸미기위해 수정할 것이다.  
일단, Atom을 설치한다. 아래 Atom 이미지를 클릭하면 된다.


<a href="https://atom.io/" target='_blank'><img src="https://1.bp.blogspot.com/-6abywUcMtCs/WMwWYgONyPI/AAAAAAAAAEg/7FrHLAZU12stRvLFMa7HT2uRZdXdpOclQCLcB/s400/logo_og_atom.png"></a>  
> <center>Atom : 예쁜 텍스트 에디터</center>


이제 Atom을 실행시키고, 블로그 파일들을 drag&drop 하여 수정하면 된다.  
<center><strong>블로그 수정 완료!</strong></center><br>


## Ruby 설치 및 로컬서버로 실행하기
---

이제 로컬 서버를 이용하여 실시간으로 블로그를 디버깅할 것이다.     
일단, Ruby부터 설치한다. 아래 Ruby 이미지를 클릭하면 된다.  


<a href="https://rubyinstaller.org/downloads/" target='_blank'><img src="https://discoversdkcdn.azureedge.net/postscontent/Ruby.jpg" width="510" height="200"></a>  
> <center>Ruby : Python과 비슷한 프로그래밍 언어.</center>

Ruby를 실행시키고, <span style="color:red">chcp 65001</span>를 통해 인코딩 설정을 해준다.  

    chcp 65001

> 인코딩 설정을 통해 명령어 오류를 예방힌다.

Clone한 디렉토리 위치로 <span style="color:red">cd</span>를 이용하여 이동한다.

    cd "C:/githubPages/Daki404.github.io"

 <span style="color:red">gem</span>을 이용하여 필요한 라이브러리를 설치한다. 그대로 복사 붙여넣기 한다.

    gem install bundler jekyll minima jekyll-feed tzinfo-data rdiscount

>gem이 Python의 pip과 비슷해 보인다.

최종적으로, 지킬 로컬 서버를 구동한다.

    bundle exec jekyll serve

> error가 발생한 경우, bundle update을 하고 다시 한다.

정상적으로 구동 되었다면, <http://127.0.0.1:4000/> 접속이 될 것이다.  
로컬 서버에서는 파일 변동 사항이 실시간으로 확인되므로,  
블로그 파일 디버깅이 용이하다.  

<center><strong>블로그 디버깅 완료!</strong></center><br>

## git push로 업데이트 하기
---

이제 파일을 다운해서 수정했고, 다시 저장할 차례이다.  
다시 <span style="color:red">Git Bash</span>를 실행시킨다. <span style="color:red">git add</span>를 통해 파일들을 업로드 한다.

    git add --all

> git add는 수정된 모든 파일들을 업로드 한다.

업로드 된 파일들을, <span style="color:red">git commit</span>을 통해 커밋한다.

    git commit -m "updates"

> 업로드 된 파일들을 커밋한다.

마지막으로, 커밋된 파일들을 다시 github 저장소로 업로드 한다.

    git push -u origin master

> 업로드 도중 로그인 창이 뜨면 로그인 하면 된다.

<center><strong>블로그 갱신 완료!</strong></center><br>

파일 수정은 이것저것 만지다 보면 점점 알게 될 것이다.  
html/css를 공부하여 좀 더 수정하면 좋을 듯 하다.  
git 공부를 하여 다차원적으로 다룰 수 있으면 좋을 듯 하다.  

2020-10-11 싸지방에서. 
