## Django CRUD

- 생성
  
  - HTML FORM
  
  - DB 저장 과정

- 조회
  
  - 글을 누르면  DB 값 조회

- 삭제
  
  - 버튼을 누르면 DB값 삭제

- 수정
  
  - HTML FORM + 기존 값
  
  - DB 저장 과정

## Django admin

***

python manage.py create superuser

- 사용자 계정을 생성한다.

- 이름과 비밀번호를 설정

admin.py

```python
from django.contrib import admin
from .models import Article
admin.site.register(Article)
```

- 게시글을 보고, 관리, 수정해 줄 수 있다.

## Static

***

## Django Bootstrap

***

pip install django-bootstrap5
