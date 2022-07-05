# RESTful

- `RE`presentational : 표현
  `S`tate : 상태
  `T`ransfer : 전달
  => 자원의 표현을 가지고 상태 전달

  - 자원의 표현 = HTTP URI

  - 상태 전달 = HTTP Method

    ```html
    // resource를 uri에 표현해서 주고 받을 정보에 대해 예측 가능
    
    /courses/front : 프론트 과정에 대한 정보
    /courses/back : 백 과정에 대한 정보
    /courses/front/crews/hyewon : 혜원에 대한 정보
    
    // URI에는 동사를 사용하지 않음.
    /courses/front/coaches/remove
    /courses/front/crew/append
    
    ```

    

- `1.네트워크 리소스를 정의하고 처리하는 방법`을 설명하는 `2.일련의 원칙을 기반으로 하는 아키텍처 스타일`

  1. 클라이언트와 서버가 데이터를 주고 받는 방식에 대해 정리한 원칙
     - HTTP를 잘 활용하기 위한 원칙
  2. 그 원칙으로 기반하는 아키텍처 스타일

  =>` HTTP를 잘 활용하기 위한 원칙 기반의 아키텍처 스타일`
  `*아키텍처 스타일 : 제약조건의 집합`



## REST 아키텍처 스타일

- HTTP만 따라도 `client-server, stateless, cache, layered system` 를 준수 가능
- code-on-demand(optional)
  = Javascript
- uniform interface
  - 자원이 uri로 식별되면 됨
  - resource를 만들거나 업데이트, 삭제 할 때 HTTP message에 표현을 담아 전송하여 달성하면 됨.
  - 위의 두 조건은 대체로 만족 함.
  - `self-descriptive messages`
  - `hypermedia as the engine of application state(HATEOAS)`



### self-descriptive messages

- 메시지는 스스로를 설명해야 한다?

  ```http
  GET / HTTP/1.1 => 목적지가 빠져 있음.
  
  GET / HTTP/1.1
  Host: www.example.org => 목적지 추가하면 self-descriptive
  
  
  #response
  HTTP/1.1 200 OK
  [ {"op": "remove", "path": "/a/b/c"}]
  
  => 어떤 문법으로 작성되었는지 해석할 수없음.
  => Content-Type: application/json과 같이 content-type header 필요
  => 여기 까지해도 사실은 op가 무슨뜻인지, path가 무엇을 의미하는지 알 수 없음.
  => Content-Type: application/json-patch+json 
  json-patch+json 이라는 미디어 타입이라는 것으로 정의 되어있는 명세, 이런 명세를 찾아가 이해한 다음 이 메시지를 해석하면 그제서야 이해할 수 있게 됨
  
  ```





### HATEOAS

- 애플리케이션의 상태는 Hyperlink를 이용해 전이되어야 한다.
  - HTML은 a tag를 통해 그다음 상태로 전이가 가능 함 = HATEOAS 만족.



### 왜 Uniform Interface가 필요할까?

- 독립적 진화

  - 서버와 클라이언트가 각각 독립적으로 진화 한다, 즉 서버의 기능이 변경되어도 클라이언트를 업데이트할 필요가 없다.
    => REST를 만들게 된 계기: 'How do I improve HTTP without breaking the Web'

  

  

  



`*참고자료`

[테코톡](https://www.youtube.com/watch?v=NODVCBmyaXs)

[NAVER-DEVIEW](https://tv.naver.com/v/2292653#comment_focus)