# OAuth

- 다른 웹사이트 상의 자신들의 정보에 대해 `접근 권한을 부여`할 수 있는 공통적인 수단 개방형 표준
- 구글, 페이스북, 깃헙 로그인등이 사용하는 인증 절차 = OAuth

![image-20220712215829367](OAuth.assets/image-20220712215829367.png)

![image-20220712215847256](OAuth.assets/image-20220712215847256.png)





## 1.0 vs 2.0

- 인증 절차 간소화
  - 기능 단순화 및 규모 확장성 지원을 위해 디지털 서명 기반의 암호화 => HTTPS의 암호화에 맡김
- 용어 변경
- 다양한 인증 방식 제공
  - Authorization Code Grant
  - Implicit Grant
  - Resource Owner Password Credentials Grant
  - Client Credentials Grant
  - Device Code Grant
  - Refresh Token Grant



## 장점

- 사용자 : 서비스에 ID/PW를 알려주지 않아도 되며 원할 때 액세스 토큰의 궈한 취소 가능
- 서비스 : 유저의 액세스 토큰만 가지고 있으면 되며, 사용자의 ID/PW 없이 허가 받은 API 접근 가능







`* 참고 자료`

[테코톡](https://www.youtube.com/watch?v=JZgD8aPkHSc)