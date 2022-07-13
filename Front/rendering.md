## 브라우저 구조

![image-20220713225437599](C:\Users\multicampus\AppData\Roaming\Typora\typora-user-images\image-20220713225437599.png)

- User Interface : 주소 표시줄, 이전/다음/새로고침 버튼 등 웹 페이지를 제외하고 사용자와 상호작용
- Rendering Engine : HTML과 CSS를 파싱하여 요청한 웹 페이지를표시
- Broser Engine : 유저 인터페이스와 렌더링 엔진을 연결
- 네트워킹, UI 백앤드, 자바스크립트 인터프리터(`V8`), 데이타 저장소등



## Rendering Engine

- 브라우저 별로 다름, Chrome은 Blink
- HTML, CSS, JS, 이미지등 웹 페이지에 포함된 모든 요소를 화면에 보여줌
- 업데이트가 필요할 때, 효율적으로 렌더링 할 수 있도록 자료 구조 생성



### Critical Rendering Path

![image-20220713225940041](C:\Users\multicampus\AppData\Roaming\Typora\typora-user-images\image-20220713225940041.png)



1. DOM tree 및 CSSOM tree 생성
   - DOM tree : HTML 파싱하여 DOM 노드로 이루어진 트리 생성
   - CSSOM tree : DOM이 어떻게 화면에 표시될지 알려주는 역할, 트리 구조
2. render tree 생성
   - 화면에 표시되어야할 모든 노드의 컨텐츠, 스타일 정보 포함(DOM + CSSOM tree)
   - Document 객체부터 각 노드를 순회하며 각각에 맞는 CSSOM에 맞는 규칙을 적용, 렌더와 맞는 요소를 render tree에 포함
   - meta tag, display none은 render와 관계 없어 render tree에 포함되지 않음.
3. Layout (reflow)
   - 각 노드들의 스크린에서의 좌표에 따라 위치 결정
4. Paint (repaint)
   - 실제 화면에 그리기

​	=> 우리가 보는 UI 완성 



`* 참고자료`

[테코톡](https://www.youtube.com/watch?v=PN_WmsgbQCo&t=218s) : Virtual DOM

[테코톡](https://www.youtube.com/watch?v=sJ14cWjrNis) : 브라우저 렌더링