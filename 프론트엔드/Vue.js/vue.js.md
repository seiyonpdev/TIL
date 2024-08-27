
#### Vue에서 뭐가 안될 때
- 개발자도구에서 vue devtools가 안 뜰 때에는 브라우저가 못 찾는 것이니 브라우저를 껐다 켠다
- Vue devtools에서 App 구조가 안 뜰 때에는 vue devtools 왼쪽의 뷰 마크 아래에 components 탭과 timeline 탭을 왔다갔다 한다

- Vetur 확장 프로그램은 ESLint와 부딪혀서 import문에 에러를 띄운다
	- from “(여기에 자꾸 빨간줄 뜬다)“;

#### Vue
- Vue는 MVVM 패턴의 뷰모델(ViewModel)레이어에 해당하는 화면(View)단 라이브러리

- 화면이 View, 화면을 구성하는 html을 조작할 수 있게 하는것이 [[DOM]], DOM을 조작하는 것이 자바스크립트
- 화면에서 키보드나 마우스 입력같은 이벤트가 발생하면 ViewModel에 속한 DOM Listener가 듣고 자바스크립트에 있는 데이터를 바꿔주거나 지정했던 특정 로직을 실행한다
- 자바스크립트의 데이터가 바뀌면 Data Bindings를 타고 화면에 반영한다

#### Reactivity
- 반응성
- 뷰의 핵심적인 기능
- 데이터의 변화를 라이브러리에서 감지해서 알아서 화면에 반영한다
