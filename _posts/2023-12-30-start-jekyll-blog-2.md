---
title : Jekyll Chirpy 테마 사용하여 블로그 만들기
date : 2023-12-30 18:00:00 +0900
categories : [jekyll, chirpy]
tags : [jekyll, chirpy, github-blog, github, blog]
---

> Jekyll Chirpy 테마를 사용하여 블로그 만드는 방법입니다.
>
> 개발 환경은 Windows 11 Pro입니다.
<hr />

## 로컬 환경 설정
Jekyll은 **Ruby** 기반의 정적 사이트 생성기입니다. 따라서 Ruby를 설치해야 합니다.  
또한, **Node.js**를 설치해야 합니다.  
이는 블로그를 초기화할 때 dist 폴더에 몇 가지의 JavaScript 파일을 생성시키는데, 이때 Node.js 명령어를 사용하기 때문입니다.  
dist 폴더에 .js 파일이 없으면 **Github Actions**에서 빌드할 때 오류가 납니다.

#### 설치해야 하는 것 목록
- **Ruby (WITH DEVKIT x86)**
- **Node.js (LTS 버전)**

#### 개발 환경 구축
1. **Ruby 설치**  
Ruby를 설치하기 위해서 <a href="https://rubyinstaller.org/downloads/" target="_blank">https://rubyinstaller.org/downloads/</a> 에 접속합니다.  
**RubyInstallers > WITH DEVKIT > Ruby+Devkit 3.3.0-1 (x86)** 을 클릭하여 설치 파일을 다운로드 합니다.  
3.3.0-1은 블로그 글을 포스팅할 때의 Ruby 최신버전이며,  
버전은 다르더라도 반드시 **WITH DEVKIT**에서 **x86** 을 다운로드 해야합니다.  
(**Tip.** Jekyll은 32bit입니다.)
<br />
<img src="../../assets/img/posts/start-jekyll-blog-2/ruby-download.png" alt="ruby 설치">
<br />
설치 파일이 다운로드 되면 실행하여 프로그램 설치를 진행합니다.
<br /><br />
체크 하는 것이 나오면 **모두 체크 후 Next 클릭, Install 클릭**을 합니다.  
설치 완료 후 **ridk install 체크 후 Finish**를 클릭합니다.  
그렇게 하면 cmd창이 열리는데, **Enter**를 눌러서 설치를 진행하고, 설치가 끝나면 **Enter**를 한 번 더 누르면 설치 프로그램이 종료됩니다.
<br /><br />
설치 후에 cmd를 열어서 설치된 **Ruby의 버전**을 확인합니다.
<br /><br />
**cmd에서 Ruby 버전 확인 방법**
```
ruby -v
````
<br /><br />
2. **Node.js 설치**  
Node.js를 설치하기 위해서 <a href="https://nodejs.org/en" target="_blank">https://nodejs.org/en</a> 에 접속합니다.  
**Download Node.js > LTS** 를 설치 파일을 다운로드 합니다.  
<img src="../../assets/img/posts/start-jekyll-blog-2/node-download.png" alt="Node.js 설치">   
설치 파일이 다운로드 되면 실행하여 프로그램 설치를 진행합니다.  
계속 **Next**를 클릭하고, **Finish** 버튼을 클릭하면 설치가 완료된 것입니다.
<br /><br />
**cmd에서 Node.js 버전 확인 방법**
```
node -v
```
<br /><br />
또한, cmd에서 Node.js 환경변수 라이브러리 설치를 설치합니다.
<br /><br />
**cmd에서 환경변수 라이브러리 설치**
```
npm install -g win-node-env
```

## Chirpy 테마 설치
본격적으로 Jekyll 블로그를 구축해보겠습니다.

#### Chirpy 테마 fork
jekyll-theme-chirpy 레포에서 <a href="https://github.com/cotes2020/jekyll-theme-chirpy/fork" target="_blank">Fork</a>를 합니다.
이때 Repository name은 `[github usename].github.io` 형식으로 입력합니다.  
저의 경우 github username이 `kimdh-dev` 이므로, `kimdh-dev.github.io` 를 입력하였습니다.
<img src="../../assets/img/posts/start-jekyll-blog-2/fork-chirpy.png" alt="테마 fork">

#### 소스 클론
블로그 소스를 본인의 컴퓨터로 가져옵니다.  
아래의 명령어는 제 github 블로그를 clone하는 방법입니다.
````
git clone https://github.com/kimdh-dev/kimdh-dev.github.io

````

#### chirpy 초기화
git bash에서 소스 폴더로 이동 후 아래의 명령어를 입력해서 chirpy 초기화를 진행합니다.
````
tools/init
```` 
명령어를 입력하면 아래의 파일들이 삭제됩니다.
- .travis.yml  
- _posts 폴더 하위의 파일들  
- docs 폴더

#### 로컬에서 실행
Jekyll을 로컬에서 실행하기 위해서 의존성 모듈을 모두 설치합니다.  
아래의 명령어를 입력하면 로컬로 실행할 때 필요한 모든 것들이 설치됩니다.
````
bundle
````

설치 후에 터미널에서 아래의 명령어를 입력해서 Jekyll을 실행합니다.
````
jekyll serve
````

정상적으로 실행됐다면 아래와 같이 출력이 됩니다.
<br />
<img src="../../assets/img/posts/start-jekyll-blog-2/jekyll-local.png" alt="로컬 실행">
<br />
브라우저를 열고 <a href="http://127.0.0.1:4000">http://127.0.0.1:4000</a> 에 접속해서 기본 블로그 화면이 뜨면 로컬로 테스트는 끝난 것입니다.  
<br />
기본 블로그 화면
<br />
<img src="../../assets/img/posts/start-jekyll-blog-2/jekyll-local-web.png" alt="로컬 접속">
<br />

## 블로그 기본 설정
_config.yml에서 기본적인 블로그 설정을 하였습니다.
- **타임존 한국으로 설정**  
timezone: Asia/Seoul

- **블로그 메인 제목 설정**  
title: 프론트엔드 개발자 김동휘 블로그

- **블로그 서브 제목 설정**  
tagline: 안녕하세요. 프론트엔드 개발자 김동휘입니다.

- **블로그 설명 설정**  
  description: >-  
   &nbsp;  &nbsp; 프론트엔드 개발자 김동휘의 개발일지

- **github usename 설정**  
  github:  
   &nbsp;  &nbsp; username: kimdh-dev

- **이름, 이메일 설정**  
  social:  
  &nbsp;  &nbsp; name: Kim Dong Hwi  
  &nbsp;  &nbsp; email: kdh.devs@gmail.com  
  &nbsp;  &nbsp; links:  
  &nbsp;  &nbsp;&nbsp;  &nbsp; - https://github.com/kimdh-dev  

- **프로필 이미지 설정**  
  avatar: https://kimdh-dev.github.io/assets/img/avatar/profile.png
## github에 배포하기
로컬에서 수정을 완료했다면 변경한 코드를 **push**합니다.  
````
git add .  
git commit -m "commit message"  
git push orgin master  
````

정상적으로 push되었다면 github에서 현재 레포지토리의 **Github Actions**에서 빌드가 진행중이어야 합니다.  
빌드가 끝났다면 아까 Fork할 때 입력한 Repository name으로 접속했을 때 블로그 화면이 뜹니다.  
(Jekyll 블로그는 Github에 푸시할 때마다 자동으로 빌드 및 배포가 진행됩니다.)

Actions에서 빌드 중인 사진
<br />
<img src="../../assets/img/posts/start-jekyll-blog-2/deploy-github-actions.png" alt="Actions 빌드">
<br />

빌드 완료 후 웹사이트에 접속했을 때 화면 (<a href="https://kimdh-dev.github.io/">https://kimdh-dev.github.io/</a>)
<br />
<img src="../../assets/img/posts/start-jekyll-blog-2/deploy-blog-web.png" alt="빌드된 웹사이트">
<br />

## 참고
- window에서 ruby 설치하기: <a href="https://seong6496.tistory.com/256" target="_blank">https://seong6496.tistory.com/256</a>
- Jekyll Chirpy 테마 사용하여 블로그 만들기: <a href="https://www.irgroup.org/posts/jekyll-chirpy/" target="_blank">https://www.irgroup.org/posts/jekyll-chirpy/</a>
- github pages 블로그 만들기 - 테마 적용하기(Chirpy): <a href="https://ree31206.tistory.com/entry/github-pages-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0-%ED%85%8C%EB%A7%88-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0Chirpy" target="_blank">https://ree31206.tistory.com/entry/github pages 블로그 만들기 - 테마 적용하기(Chirpy)</a>