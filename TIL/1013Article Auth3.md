## Article CRUD

***

> ModelForm 을 활용한

`User CRUD`

- 인증, 별도의 절차가 필요하다

- 암호화

- 클래스 `Abstract User` 상속받아 활용, 

- `Abstract User` 는 비밀번호 저장

`Auth`

- django.contrib.auth  에서 받아옴

`HTTP`

- Conectionless( 단방향 통신으로 전송할 수 있으며 응답이 가능)

- stateless

`결과적으로 로그인이란??`

- 그 이후의 요청을 인증

- 응답으로 쿠키를 던져줌

- 다음번 요청 때는 쿠키랑 같이 요청을 전달하므로, 기존 정보를 즉각 인식

`session`

- 연결 상태를 정의

- 쿠키 안에 session id 정보가 들어있고, 이를 같은지 DB서버가 테이블에서  확인

`UsercreationForm`

- from django.contrib.auth.forms

`Login_required`

- from django.contrib.auth.decorators

## 2교시

***

회원 정보 수정을 위해 

- URL: /accounts/<int:pk>/update/

- 여기서, 그냥 로그인한 유저의 정보만 수정하면 되지 않을까?

URL은 /accounts/update, 단 로그인을 한 사용자

GET 요청 : Form

POST 요청 : 실제 수정

`그러면?`

- UserChangeForm 사용

`이유는?`

- 우리와 사용자는 `비밀번호`가 다르다

- UserCreationForm = 비밀번호 두개를 받아 일치하는 로직 포함

- UserChangeForm = 비밀번호 두개를 받을 필요가 없음, 로직이 다름

- 수정은 내 마음대로 로직을 만들면 된다

- 일반적으로 모든 회원가입정보가 바뀌는 경우는 없다.

`언제 login_required?`

- 로그인이 필요한 상황...

- request.user로 유저 객체를 쓰는 view 함수에선 무조건 쓰는 것을 추천

- 
