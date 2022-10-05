## 📗 Django 2일차

___

- 내용정리
  
  - 프로젝트마다 다른 패키지사용 &rarr;  가상환경
  
  - 사용자 &rarr; Django server &rarr; DB /요청
  
  - DB &rarr; Django server &rarr; 사용자 / 처리

- requirements.txt 관리
  
  - 가상환경을 생성할 떄 관리하여 편리하게 사용할수 있는 파일
  
  - 프로젝트 진행 시 만들어서 관리해보자

***

- 실습 풀이
  
  - URL &rarr; VIEW &rarr; TEMPLATE 순서대로 수정
  
  - path in URL에서...
    
    - 1. 주소를 지정
      
      2. 어떤 VIEW를 실행할껀지 지정
      
      3. > path('',views.index),
  
  - in VIEW
    
    - 1. 인덱스를 정의해준다.
      
      2. 리턴값을 설정해준다
      
      3. > def index(request):
         > 
         >     (대충 함수 정의한다는 내용)
         > 
         >         return render(request,"index.html")
    
    - def 안 리스트는 다음과 같이 정리한다.
    
    ```py```
    list = [
        {"name"}: "object","src":"https:"
    ]
    ```


