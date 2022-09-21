## Django  시작하기

> Django = 가장 인기있는 Web Framework

- python 으로 작성된 프레임 워크

- 검증된 웹 프레임 워크

> 코드들을 모아놓은 것, 서비스 개발에 필요한 기능들을 미리 구현해서 모아놓은 것
> 
> == Framework

## WWW

- World Wide Web

- 전 서계에 퍼져 있는 거미줄 같은 연결망

## 클라이언트 - 서버 구조

- 클라이언트
  
  - 웹 사용자의 인터넷에 연결된 장치
  
  - Chrome Firefox 같은 웹 브라우저
  
  - 서비스를 요청하는 주체

- 서버
  
  - 웹페이지, 사이트 또는 앱을 저장하는 컴퓨터
  
  - 클라이언트가 웹 페이지에 접근하려고 할 때 서버에서 클라이언트 컴퓨터로 웹 페이지 데이터를 응답해 사용자의 웹 브라우저에 표시됨
  
  - 요청에 대해 서비스를 응답하는 주체

## 정적 웹 페이지

- Static Web page

- 있는 그대로를 제공

- 파일의 내용이 변하지 않고 모두에게 동일한 모습으로 전달

## 동적 웹 페이지

- Dynamic Web page

- 사용자의 요청에 따라 추가적인 수정이 이루어져 전달되는 웹 페이지

- 웹 페이지의 내용을 바꿔주는 주체 == 서버
  
  - 사용자의 요청을 받아 적절한 응답을 만들어주는 프로그램을 쉽게 만들 수 있는 프레임 워크가 바로 Django

## 소프트웨어 디자인 패턴

- 만들던 패턴데로 만드는 것

- 복잡한 커뮤니케이션이 간단해짐

- Django에선 MTV패턴이 적용

## MVC 소프트웨어 디자인 패턴

- Model - View - Controller

- 데이터 및 논리 제어를 구현하는데 널리 사용되는 소프트웨어 디자인 패턴

- Model : 데이터와 관련된 로직을 관리

- View : 레이아웃과 화면을 처리

- Controller : 명령을 model과 view 부분으로 연결

- 더 나은 업부의 분리와 향상된 관리를 제공

- 독립적으로 개발 가능

## 디자인 패턴 in Django

- MVC 패턴을 기반으로 한 MTV 패턴 사용

- 서로 크게 다른 점은 없음

| MVC        | MTV      |
| ---------- | -------- |
| Model      | Model    |
| View       | Template |
| Controller | View     |

## Model

- 데이터와 관련된 로직을 관리

- 데이터 구조 정의, 데이터베이스 기록 관리

## Template

- 레이아웃과 화면을 처리

- 화면상의 사용자 인터페이스 구조와 레이아웃 정의

- MVC 패턴에서 View 역할에 해당

## View

- Model & Template와 관련한 로직을 처리하여 응답반환

- 클라이언트의 요청에 대해 처리를 분기하는 역할

- 예시
  
  - 데이터가 필요하면  Model에 접근하여 가져옴
  
  - 가져온 데이터를 template로 보내 화면 구성
  
  - 화면을 응답으로 만들어 클라이언트에게 반환

## 가상환경 활성화

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-11-01-10-image.png)

> pip.list

- 설치된 개발환경 리스트 보기

> deactivate

- 가상환경 종료

> source server-venv/Scripts/activate

- 위 경로로 가상환경 생성

> django-admin startproject [프로젝트 이름] [시작경로]

- 위 경로로 프로젝트 생성(경로에 . 하면 현재 위치)

> python manage.py runserver

- 서버 실행

> localhost:8000

- 생성한 개인컴퓨터 로컬 서버 접속

> code .

- 위치의 vscode open

```textile
cd ..        //이전 디렉토리
mkdir test    //text 폴더 생성
cd test    //test로 이동
ls     // 뭐 있는지 보기
python -m venv [가상환경이름] [경로]     //가상환경 만들기
ls    // 확인

cd test-venv    // 만든 환경으로 들어가
내    
```
