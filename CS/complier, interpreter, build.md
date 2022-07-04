## 어셈블리어

- assembly language, 기계와 일대일 대응이 되는 컴퓨터 프로그래밍의 저급 언어

- 컴퓨터 구조에 따라 사용하는 기계어가 달라지며, 기계어에 대응되어 만들어지는 어셈블리어도 다양하다. ⇒ 통일된 언어체계로 작성한 코드의 필요성 대두, but 컴퓨터는 고급 언어로 작성한 코드를 바로 인식하지 못함. 따라서 번역해 줄 과정인 Complie 필요.

  

## Complier, Interpreter, and Build

- 어셈블리어를 번역해주는 2가지 방식

### Complier

- 프로그램 전체를 스캔하여 이를 모두 기계어로 번역
- 따라서 초기 스캔이 오래 걸리나, 초기 스캔 후 실팽하일을 만들어 놓고 다음 실행할 때 실행파일을 이용하기 때문에 전체 실행시간만 보면 인터프리터 보다 빠름.
- 고급언어 → 기계어번역 (오브젝트 코드) : complier / 오브젝트 코드 + 각종 resources → 실행파일 : Linking 이로인해 더 많은 메모리를 생성하며, 이 전체 과정을 build라고 함!
- complie ⊂ build
- 전체 코드를 스캔하는 과정에서, 모든 오류를 한꺼번에 출력해주어 실행 전에 오류를 알 수 있음.
- Java, C, C++

### Interpreter

- 실행 시 한 번에 한 문장씩 번역, 따라서 실행파일을 작성 후 실행파일을 실행하는 complier보다 실행 시간이 오래 걸림.
- 목적 코드 생성 X, Linking 과정 X ⇒ 메모리 효율 ↑
- 프로그램을 실행시키고 나서 오류를 발견하면 바로 실행을 중지 시킨다. 실행 후에 오류를 알 수 있음.
- Python, Javascript

### Build

- 기계어 → Complie하여 목적 코드 생성 → 목적코드 + resources로 Linking → 실행 파일 생성.
- 이 과정을 자동화(*매번 반복해야 하는일)한 것이 빌드 도구

- `의존성 다운, 컴파일, 이진 코드 패키징, 자동화된 테스트 실행, 프로덕션 시스템 배포`

- 규모가 작은 경우 직접 해도 되나, 규모가 커질 경우 내가 어디에 있는 소스코드를 빌드해야 할지 모름, 빌드 프로세스 일관성 유지를 위해 빌드 도구 사용
- Java진영 대표적인 빌드 도구 에는 출시 순서대로 Ant, Maven, Gradle이 있음.
  1. Ant
     - xml, 절차적, 유연성, 스크립트를 직접 명시
     - 빌드 스크립트를 짤 때 소스 코드의 위치등 모든 것을 명시 해줘야 함 ⇒ 유연성이 좋다.(but 귀찮음)
  2. Maven
     - pom.xml
     - 의존성 다운로드 가능 (Ant에 비해 간편하나, )
     - 컨벤션이 있어 사용자 의도에 맞는 로직 개발이 어려움( 유연성이 떨어짐)
  3. Gradle
     - 위 두 도구의 단점을 보완하기 위해 나온 것
     - 스크립트 규모가 작음.



`*참고 사이트`

[벨로그](https://velog.io/@jhur98/컴파일러compiler와-인터프리터interpreter의-차이)

[테코톡](https://www.youtube.com/watch?v=JgRCaVwkPE8)