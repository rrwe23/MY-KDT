## πμ΄λ―Έμ§ μλ‘λ

***

>  μ΄λ―Έμ§ μλ‘λλ₯Ό μν΄ μ΄λ€κΈ°λ₯μ κ΅¬νν΄μΌ ν κΉ?

`pillow`

- μ΄λ―Έμ§λ₯Ό κ΄λ¦¬νλ νμ΄μ¬ μ΄λ―Έμ§ λΌμ΄λΈλ¬λ¦¬

install pillow

```python
pip install pillow
```

models.py μ€κ³

```python
class Article(models.Model)
    title = modles.CharField(max_length=20)
.
.
.

    image = models.ImageField(upload_to='images/', blank=True)
# black = Trueλ₯Ό ν΅ν΄ μ΄λ―Έμ§ νλμ λΉ κ°μ΄ νμ©λλλ‘ νλ€.
```

μ΄ν `makemigrations`, `migrate`

```python
python manage.py makemigrations


python manage.py migrate
```

`μ΄ν  forms.py κ΅¬ν`

```python
# forms.py
from django import forms
from .models import Article


class ArticleForm(forms.ModelForm):
    class Meta:
        model = Article
        fields = ['title','content','image'] # λΆλ¬μ¬ κ° μλ ₯
```

`URL μ€μ `

- enctype(μΈμ½λ©) μμ±μ λ°λμ μ§μ 

- <input type="file"μ μ¬μ©ν  κ²½μ°μ μ¬μ©

```python
# html
<form action="" method="POST" enctype="multipart/form-data" >
        {% csrf_token %}
        {% bootstrap_form article_form %}
        {% bootstrap_button content="κΈμ°κΈ°" button_type="submit" button_class="btn-secondary col-3" %}

    </form>
# <enctype='multipart/form-data'> μΆκ°

<img src="{{ article.image.url }}" alt="{{ article.image }}">
# μλ‘λ λ νμΌμ κ²½λ‘λ Django κ° μ κ³΅νλ URL μμ±μ ν΅ν΄ μ»μ μ μλ€.
```

- μ¬μ©μκ° μλ‘λ ν νμΌλ€μ λ³΄κ΄ν  λλ ν λ¦¬μ μ λ κ²½λ‘λ₯Ό μ§μ 

- Djangoλ μ±λ₯μ μν΄ μλ‘λ νμΌμ  DBμ μ μ₯νμ§ μλλ€.

```python
# settings.py
MEDIA_ROOT = BASE_DIR / 'images'
MEDIA_URL = 'media/' # λΉμ΄μμ§ μμ κ°μΌλ‘ μ€μ νλ€λ©΄ λ°λμ '/'λ‘ λ
```

`views μ€μ `

- κ°μ₯ λ° κ²½λ‘μ media/images ν΄λ μΆκ°

- images ν΄λ μμ μ¬μ§λ€μ λ£μ΄μ€λ€.

```python
# request.FILES μΆκ°
def create(request):
    if request.method == 'POST':
        article_form = ArticleForm(request.POST,request.FILES)
        if article_form.is_valid():
            article_form.save()
            return redirect('articles:index')
    else:
        article_form = ArticleForm()
    context = {
        'article_form' : article_form
    }

    return render(request,'articles/new.html',context=context)
```

- article.image.url = μλ‘λ νμΌμ κ²½λ‘

- article.image = μλ‘λ νμΌμ νμΌ μ΄λ¦

`image Resizing`

> django-imagekit λΌμ΄λΈλ¬λ¦¬λ₯Ό νμ©νλ€.

`λΌμ΄λΈλ¬λ¦¬ μ€μΉ`

```python```
pip install django-imagekit

```
```python
#settings.py

INSTALLED_APP = [
    'imagekit',
]
```

```python
# models.py

# from imagekit.models import ProcessedImageField
# from imagekit.processors import Thumbnail

from django.db import models
from imagekit.models import ProcessedImageField
from imagekit.processors import Thumbnail

class Article(models.Model):
    title = models.CharField(max_length=20)
    content = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
    Updated_at = models.DateTimeField(auto_now=True)
    # image = models.ImageField(upload_to='images/',blank=True)
    image = ProcessedImageField(
        blank=True,
        processors=[Thumbnail(200,300)],
        format='JPEG',
        options={'quality':90},
    ) # μΆν κ°μ λ³κ²½νλλΌλ makemigrations μμ΄ μ¦μ λ°μ

def __str__(self):
    return self.title
```
