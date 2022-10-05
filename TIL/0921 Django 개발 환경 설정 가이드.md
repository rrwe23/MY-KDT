## Django 개발 환경 설정 가이드

## 가상환경 생성

#### ✔ Git bash

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-33-40-image.png)

#### cd ~ 를 통해 초기 지점으로 이동

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-34-38-image.png)

> ✔ pwd 를 통해 경로를 확인 할 수 있다.

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-35-31-image.png)

#### mikir (폴더 이름) 을 통해 가상환경 이름 폴더 생성

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-38-01-image.png)

#### cd (서버 이름) 을 통해 입장

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-39-46-image.png)

> pip list 를 통해 설치된 디렉토리를 열람할 수 있다.

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-40-37-image.png)

#### python -m venv [가상환경이름]

- 가상환경을 생성해준다

- 이름은 자유

- ls -a 를 통해 환경 파악

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-47-26-image.png)

#### source [가상환경이름]/scripts/activate

⚡ 가상환경을 작동한다.

- (-venv)를 통해 확인 가능

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-51-25-image.png)

#### pip install django==(버전)

- 원하는 버전의 장고 설치

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-54-39-image.png)

#### deactivate

- 가상환경 종료

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-14-55-21-image.png)

#### django-admin startproject [프로젝트 이름] [시작 경로]

- django-admin : 장고 관리

- startproject : 프로젝트 시작

- 지금 폴더에서 시작할거면 [.]

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-15-02-03-image.png)

#### code .

- 폴더 열기

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-15-03-23-image.png)

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-15-04-16-image.png)

#### manage.py 실행을 통해 코드 실행

> python manage.py runserver

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-15-05-55-image.png)

## ✔서버 확인

> localhost:8000

- 로컬 호스트를 통해 서버에 접속 할 수 있다.

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-21-15-07-40-image.png)
