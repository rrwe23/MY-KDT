## namespace

***

- 개체를 구분하기 위해 필요

- urls 에서 path에 name을 걸어줘서 개체를 구분한다.

- URLs

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-28-09-34-22-image.png)

- HTML

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-28-09-34-39-image.png)

- name 지정시 변수명이 같다면 가장 마지막에 선언한 이름을 따라간다.

***

## URL  namespace

- 서로 다른 앱에서 동일한 URL 이름을 사용하는 경우에도 지정된 URL을 고유하게 사용 할 수 있음

- app_name 을 작성한다.
  
  ![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-28-09-51-34-image.png)

![](C:\Users\이주현\AppData\Roaming\marktext\images\2022-09-28-09-51-24-image.png)



- [참고] DRY 원칙
  
  - Don't Repeat Yourself
  
  - 더 품질 좋은 코드를 작성하기 위해서 알고 따르면 좋은 소프트웨어 원칙들 중 하나
  
  - 소스 코드에서 동일한 코드를 반복하지 말자

- Django 설계 철학
  
  - 표현과 로직(view)을 분리
  
  - 중복을 배제
  
  ## framework의 성격

- 독선적
  
  - 대체로 특정 문제내에서 빠른 개발방법을 제시
  
  - 올바른 방법이란 문서화가 잘 되어있기 때문
  
  - 유연한 해결책은 제시하지 못함

- 관용적
  
  - 올바른 방법에 대한 제약이 거의 없음
  
  - 적절한 도구들을 이용할 수 있는 자유도가 높음
  
  - 하지만 개발자들이 스스로 그 도구들을 찾아야 한다는 수고가 필요

- 다소 독선적
  
  - 양쪽 모두에게 최선의 결과를 가져다준다고 강조

- 결국 제일 중요한 것을 생산성

- 우리가 온전히 만들고자 하는 것에만 집중할 수 있게 도와주는 것

- '수레바퀴를 다시 만들지 말라'

***

## Design Pattern

- 공통적인 설계 문제를 해결

- 지식과 지혜들이 쌓여서 작동



- MVC 소프트웨어 디자인 패턴
  
  - Model - View - Controller
  
  - 하나의 큰 프로그램을 세가지 역할로 구분한 개발 방법론
  
  - model : 데이터와 관련된 로직을관리
  
  - view : 레이아웃과 화면을 정리
  
  - controller :  명령을 model과 view 부분으로 연결

- MVC의 목적?
  
  - 관심사 분리
  
  - 향상된 관리
  
  - 독립적 유지 보수

- Database
  
  - 체계화된 데이터의 모임
  
  - 조직화된 데이터를 수집하는 저장 시스템

- database 기본 구조?
  
  - Schema
    
    - 뼈대
    
    - 데이터베이스에서 자료의 구조, 표현방법, 관계 등을 정의한 구조
  
  - table
    
    - 필드와 레코드를 사용해 조직도니 데이터 요소들의 집합
    
    - 관계라고도 부름
    
    - 필드 (속성, 컬럼)
    
    - 레코드(튜플, 행)

- PK(primary Key)
  
  - 기본키
  
  - 각 레코드의 고유한 값
  
  - 절대로 중복될 수 없는 단일 값
  
  - 예시 : 주민등록번호

## 추가 필드 정의

- models.py 작성
  
  - 모델 클래스를 작성하는 것 == DB 테이블  스키마 작성
