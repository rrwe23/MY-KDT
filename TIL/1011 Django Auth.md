## Django Auth

***

회원가입, 로그인

> 어떠한 부분이 비슷하면서 어떠한 부분이 다를까?

- 인증, 권한부여

Django Auth

- Django authenication system은 인증과 권한 부여를 함께 제공
  
  - user
  
  - 권한 및 그룹
  
  - 암호 해시 시스템
  
  - Form 및 View 도구
  
  - 기타 적용 가능한 시스템

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-10-11-09-47-59-image.png)

- Authentication
  
  - 신원 확인
  
  - 사용자가 자신이 누구인지 확인하는 것

- Authorization
  
  - 권한 부여
  
  - 인증된 사용자가 수행할 수 있는 작업을 결정

사전 설정

- 앱을 생성하고 등록해야 한다.

- 되도록 앱 이름을 accounts로 지정하는 것을 권장

- Django 는 새 프로젝트를 시작하는 경우  기본 User 모델이 충분하더라도 커스텀 User 모델을 설정하는 것을 강력하게 권장

- 필요한 경우 나중에 맞춤 설정 할 수 있기 때문

암호 관리

- 암호화가 된 후 복호화가 되면 안된다. (단방향)

- 
