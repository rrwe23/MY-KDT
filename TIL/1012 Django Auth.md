## Auth Q&A

***

- Q. auth.User를 사용하지 않고 accounts.User를 만드는 이유?
  
  - 권장사항
  
  - 나중에 필요한 순간에 커스텀하기 위함이다.

- Q. UserCreationForm 의 Custom?
  
  - UsercreationForm => ModelForm 상속 받아서 만들고 있다.
  
  - 모델과 필드가 ModelForm 정의에서 가장 중요하다

- get_user_model의 사용 이유?
  
  - User 모델이라는 건 결국 변경이 가능
  
  - 변수화를 통해서 호출하는 것이 가장 베스트!
  
  - redirect('articles:index) == /articles/ {% url 'articles:index' %}
  
  - 유저 모델 클래스는 어딘가에 존재 이를 호출하여 사용하자
  
  - 그러면 알아서 AUTH_USER_MODEL에 정의된 클래스를 준다

***

로그인에 대한 이해

`HTTP`

- 비 연결 지향 : 서버는 요청에 대한 응답을 보낸 후 연결을 끊음

- 무상태 : 연결을 끊는 순간 통신이 끝나며 정보가 유지되지 않음
  
  - 주고받는 메시지들을 완전히 독립적

`쿠키`

- 서버가 사용자의 웹 브라우저에 전송하는 작은 데이터 조각

- 사용자의 컴퓨터에 설치되는 작은 기록 정보 파일

- 서로 다른 요청이 동일한 브라우저로부터 발생한 것인지 판단할 때 사용

- 세션 관리, 개인화, 트래킹을 목적으로 사용

`세션`

- 사이트와 특정 브라우저 사이의 상태를 유지시키는 것

- 서버가 특정 ID를 발급, 클라이언트는 쿠키에 ID를 저장

`세션 쿠키`

- 보안이나 정책에 따라 당하지만 시간이 지나면 상한다.

로그인 기능

- URL : GET/accouts/login/
  
  - 처리
  
  - 템플릿 사용자에게  form 제공

- URL : POST/accouts/login/
  
  - 처리
  
  - 로그인 로직처리
  
  - 사용자인지 확인하고  Django_session 테이블에 저장, 쿠키 주기
  
  - (성공)게시글 목록 페이지로 redirect
  
  - (실패) 로그인 form

```python```
def login(request):
    if request.method =='POST':
        form = AuthenticationForm(request, data=request.POST)
        if form.is_vaild():
            # 세션에 저장
            # login 함수는 request, user 객체를 인자로 받음
            # user 객체는 form에서 인증     
         auth_login(request, form.get_user())
         return redirect('articles:index')
        else:
            form = AuthenticationForm()
        context = {
    'form' : form
}  

    return render(request, 'accounts/login.html',context)

```
`AuthenticationForm`

- 로그인을 위한 빌트인 폼

  - 로그인을 하고자 하는 사용자 정보를 입력받음(username,password)

  - 일반 폼을 상속 받고 있다

`Login()`

- login(request,user,backend=None)

- 인증된 사용자를 로그인

  - 유저의 ID 세션에 저장하여 세션을 기록

- HttpRequest 객체와 User 객체가 필요

  - 유저는 반드시 인증된 유저 정보여야 한다.

  - authenicate()함수를 활용한 인증

  - AuthenticationForm을 활용

`Login Logic`

- 일반적인 모델폼 기반의 Create 로직과 동일

- But, form으로 필수 인자 구성이 다름

- DB에 저장하는 것 대신 세션에 유저를 기록하는 함수 호출

  - View 함수와 이름이 동일하여 변경하여 호출

  - login URL 이 /accounts/login/ 에서 변경되는 경우 ,setting.py login_URL 을 변경



`get_user()`
```
