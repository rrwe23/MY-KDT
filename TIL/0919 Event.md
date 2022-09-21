## Event

> 특정한 이벤트가 발생하면 할 일을 등록하자

- 네트워크 활동이나 사용자와의 상호작용 같은 사건의 발생을 알리기 위한 객체

- EventTarget.addeventListener(type, listener,[options])
  
  - 지정한 이벤트가 전달 될 때 호출할 함수 설정
  
  - type = 반응할 이벤트
  
  - Listener = 이벤트 발생 시 알림을 받는 객체

> event.preventDefault()

- 현재 이벤트의 기본 동작을 중단

- HTML요소의 기본 동작을 작동하지 않게 막음

- 이벤트를 취소할 수 있는 경우 전파를 막지 않고 이벤트를 취소
