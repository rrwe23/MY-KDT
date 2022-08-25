## 깃허브 - 형상 관리 프로그램

​    \- 프로젝트 관리 프로그램

​    분산 버전 관리



## markdown - 문서정리도구 = 존 그루버가 만든 텍스트 기반의 가벼운 마크업 언어

최소한의 문법으로 구조화시켜준다

ex - 기술 블로그

## typora - markdown editor

실시간으로 전환되서 보여준다



hypen, *(asterisk)

\##() = Heading

\#() = Heading (bigger)

\#의 갯수에 따라 h1~h6까지 적용



## list (-) 순서가 없는 리스트

 tap = 들여쓰기

 tap + shift = 들여쓰기 되돌리기

 1.

 2.

 3.



## 코드 블록 = backtick (`) 기호 3개를 활용하여 작성 (``` ```)

 

 코드 블록에 특정 언어를 명시하면 Syntax Highlighting 적용 가능











사과

- 바나나
  - 미니 바나나



### 순서가 있는 리스트

아침에 일어나서 KDT 교육 듣기

1. 세수하고 양치
2. .산책
3. Syllaver 홈페이지 접속.
   1. 로그인
   2. 대시보드 확인

4. 유튜브 라이브 접속
   1. 인사를 남긴다



## 코드 블록

` 기호 3개를 활용하여 작성

특정 언어를 명시하면 Syntax highlighting 기능

```python
print ('hello')
# 주석
```

```python
print('hello')
# 주석?

```

## [실라버스 링크](h?/?ttps://????) 를 통해 링크를 작성 가능

![문자열](url)을 통해 이미지 사용 가능

특정 파일을 포함하여 연결 시킬 수 있음



![06230046](C:\Users\이주현\Desktop\06230046.png)

상대경로로 설정하면 경로에 상관없이 열람 가능

- 상대경로
- 마크다운.assets폴더를 같이 공유하면!



## 표

| 이름 |                        |
| ---- | ---------------------- |
| 류진 | 노션이랑 비슷하네요    |
| 이성 | 빨간색 프로그램이 뭐죠 |
|      |                        |

본문 - 표 - 표 삽입 (Cntl + T)

## 인용문

">"를 통해 인용문을 작성

> 아 코딩 힘들다





## 텍스트

**굵게**

Ctrl +  b = 볼드체

Cnrl + i = 이탤릭체

굵게** (양쪽에)

기울림 * (양쪽에)

*기울임*

~~취소선~~

취소선:~~(양쪽에)



수평선"---"

---

## 😊기타정리



띄어쓰기 있는것

- 제목(#)
- 목록(-,1.)

띄어 쓰기 없는 것

inline code block



이모지 : window  + (.)



fenced code block

``` ㅁㄴ이렁아 ```

### 소스코드 모드

Cntl + /

### 링크 열기

Cntl + 클릭



## 마크다운

- [마크다운 예시](./read me.md)
- [이미지폴더](./images)



## CLI 환경

Command Line Interface

#### 기초 명령어

- pwd (print working directory) = 현재 디렉토리 출력
- cd (change directory) = 디렉토리 이동
- ls (list) 목록
- mkdir( make directory) = 디렉토리 생성
- touch = 파일의 날짜와 시간을 수정( 0바이트 빈 파일 생성)
- cd(띄우기).. = 뒤로 나가기
-  tab= 자동완성
- rm( remove) = 파일 지우기
- rm -r = 폴더 지우기( 반복을 통해 모든 디렉토리 제거 명령)
- Ctrl  + L =  칠판 지우기



## GIT

분산 버전 관리 시스템

리눅스 토르발즈에 의해 제작

컴퓨터 파일의 변경사항을 추적

### (master)

변동사항이 기록되고 있는 문서



Working Directory   == 보고서 (빨강)



staging Area  == 내가 버전 기록 파일들을 모은다! ( 테썹)  (초록)



Repository(커밋)  == 버전들이 기록되는 곳



## 기본 명령어 -  .add(1에서 2통)

git add <file>

working directory 상의 변경내용을 staging area에 추가하기 위해 사용

- untracked 상태의 파일을 staged로 변경

- modified 상태의 파일을 staged로 변경

## commit == 2통에서 3통으로 이동

### git commit-m '<커밋메세지>'



- staged 상태의 파일들을 커밋을 통해 버전으로 기록

### git은 파일을 modified, staged committed 로 관리



## 기본명령어 - log(3통 확인)

$ git log

- 현재 저장소에 기록된 커밋을 조회
- 다양한 옵션을 통해 로그를 조회할 수 있음

git log - 1 = 최근 1개의 커밋을 가져오기







## git status(1통,2통 확인)

- 커밋 확인
- 커밋할 것이 없다 == staging area 가 비어있다
- 빨간 글씨 ==> 1통

### git init

로컬 저장소 생성

````
# Git Status

## a.txt 파일을 만든 직후

> 빨간 글씨 => 1통

```bash
$ git status
On branch master

# 트래킹이 되고 있지 않은 파일?
# => 1통 (working directory)
# => 한번도 git으로 관리되고 있지 않은 파일!
Untracked files:
# git add 사용해봐...
# 포함시키기 위해서 / 커밋이 될 것 => 2통에 넣으려면
  (use "git add <file>..." to include in what will be committed)
        a.txt

# 커밋할 것은 없어 => 2통이 비어있어
# 하지만(but) 트래킹되지 않은 파일은 존재한다. 
# (git add 사용해서 트래킹해)
nothing added to commit but untracked files present (use "git add" to track)
```

## b.txt 파일을 만들고 add한 이후

> 초록 글씨 => 2통

```bash
$ git status
On branch master
# (커밋될) 변경사항들 => 2통
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
  		# 새로운 파일: b.txt
        new file:   b.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        a.txt

```

# a.txt 파일과 b.txt 파일을 모두 add한 이후 커밋까지

```bash
$ git status
On branch master
# 2통, 1통 모두 클린~!
nothing to commit, working tree clean
```
````



## Git add <파일명>

특정 파일의 변경사항 추가



# Git 실습

$ rm -rf .git  ===초기 마스터 제거



## 1.(master) 있는 곳에서는 git init을 하지 않는다



## 2. git 명령어를 입력할 때에는 항상 경로를 잘 보자



## 3. 명령어의 결과 영어를 잘 읽자















