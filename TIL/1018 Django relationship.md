## 📗Django(sw)

> 여기까지의 과정...

- 요청 - 응답

- APP / MTV  패턴

- 로직 &rarr; Form 데이터 받음

- Model (단일 테이블)

- 게시판(CRUD)

- ModelForm게시판(IRVD)

- 회원가입

- 요청 - 응답(쿠키-세션)

- 로그인

## A one - to - many relationship

***

> 관계형 데이터베이스 하면..? == 표!

`RDB 에서의 관계`

- 1:1
  
  - 이름, 비밀번호 , 이메일

- 1:N
  
  - 사용자의 글, 댓글

- M:N
  
  - 다음주에 공개..

`Foreign Key`

- 외래 키

- 관계형 데이터베이스에서 다른 테이블의 행을 식별할 수 있는 키

- 참조되는 테이블의 기본 키를 가리킴

- 키를 사용하여 부모 테이블의 유일한 값을 참조(참조 무결성)

> 댓글 기능을 구현하려면?
> 
> 댓글목록, 댓글작성, 댓글 생성 기능 등?

`Foreign Key arguments-on_delete`

- 외래 키가 참조하는 객체가 사라졌을 때, 외래 키를 가진 객체를 어떻게 처리할 것인지 정의

- on_delete
  
  - CASCADE : 부모 객체(참조 된 객체)가 사라졌을때, 이를 참조하는 객체도 삭제

`Comment 모델 정의`

- 외래 키 필드는 위치와 관계없이 마지막에 작성됨

- 인스턴스 이름은 참조하는 모델 클래스 이름의 단수형으로 작성하는 것을 권장

```python
# models.py 에서 작성
class Comment(models.Model):
    content = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
    article = models.ForeignKey(Article, on_delete=models.CASCADE)
```

모델에 대한 수정사항이 발생했기 때문에 migration 과정 진행

```python
python manage.py makemigrations


python manage.py migrate
```

> 모델 필드로 인해 작성된 컬럼의 이름이 ____.id 로 나옴
> 
> 그렇기에 참조하는 클래스 이름의 소문자로 작성하는 것을 권장

`shell_plus 실행하기 전에!`

- pythin pip 설치가 필요하다

```python
$ pip install django-extensions
$ python manage.py shell_plus
```

- 이후 앱 추가가 필요하다.

```python
# settings.py
INSTALLED_APPS = [
    'django_extensions',
]
```

`셋팅후 shell_plus 실행`

```python
$ python manage.py shell_plus
```

`댓글 생성`

```python
# Comment 클래스의 인스턴스 comment 생성
comment = Comment()


# 인스턴스 변수 저장
comment.content = 'first comment'


# DB에 댓글 저장
comment.save()
```

```python
# 게시글 생성 및 확
```

```python
# 13번 게시글의 모든 댓글을 알고자 한다면?

Comment.objects.filter(aritcle_id=13)
```

```
#Article 객체의 모든 댓글

aritcle.comment_set.all()
```
