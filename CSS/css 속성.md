- 박스 속성 : 웹 페이지의 레이아웃을 구성할 때 가장 중요
	- width : 가로
	- height : 세로
	- margin : 바깥쪽 여백
	- padding : 안쪽 여백
	- border : 테두리
		- border-width : 테두리 두께
		- border-style : 테두리 모양
		- border-color : 테두리 색
		- border-radius : 테두리 둥글게
	margin과 padding은 top, bottom, left, right로 지정해서 여백을 줄 수 있다
	방향을 각자 따로 지정하고 싶으면 다음과 같은 형식으로 지정한다
	위부터 시계방향으로 위 오른쪽 아래 왼쪽 순이다
	ex.) margin : (위아래) (좌우)
	ex.) margin : (위) (아래) (좌우)
	ex.) margin : (위) (오른쪽) (아래) (왼쪽)

- 가시 속성 : 태그가 화면에 보이는 방식을 지정
	- display
		- none : 화면에 보이지 않는다
		- block : 박스 형식으로 지정
		- inline : 인라인 박스 형식으로 지정. 인라인은 크기를 변경할 수 없다
		- inline-block : 블록과 인라인의 중간 형태로 지정. 인라인 블록은 크기 변경 가능

- 배경 속성
	- background : 배경
		- background-image : (url) ← url은 홑따옴표로 감싸야 한다
		- background-size : 배경이미지 사이즈
		- background-repeat : 배경이미지 반복
			- repeat-x : x축으로 반복
			- repeat-y : y축으로 반복
			- no-repeat : 반복 X
		- background-attachment : 배경이미지를 화면에 고정. 스크롤 올려도 안 올라가게.
		- background-position : 배경이미지의 위치 지정
			형식 : background-position : (가로위치%) (세로위치%);

- 글자 속성
	- font : (italic) (bold) (size) (family) **입력 순서따짐**
		- font-size : 폰트[[크기 단위|크기]]
		- font-family : 글꼴 설정
		- font-style : 이탤릭 적용
		- font-weight : 볼드 적용
	- color : 글씨 색
	- text-align : 글자 정렬
	- line-height : 줄 간격
	- text-decoration : 글 꾸미기. none으로 설정하면 링크의 밑줄 없앨 수 있음

- 위치 속성
	위치가 지정된 요소와 지정되지 않은 요소가 섞이면 문제가 발생한다.
	이때 지정되지 않은 요소에게 공통의 부모 요소를 주고 relative와 height를 설정해야 한다
	- position : 위치 지정 형식 설정
		- 절대 위치 : absolute, fixed
			absolute는 스크롤을 내리면 사라진다
			fixed는 그 자리를 계속 지키면서 같이 내려온다
		- 상대 위치 : relative, static
		위치 지정 형식 설정 후 실제로 위치를 지정해야 그대로 나타난다.
		ex.) left : 10px; top : 10px; right~ bottom~
		요소를 앞으로 나오게 하고 싶으면 z-index를 사용한다
		ex.)z-index : 100;
	- overflow : 자식 요소가 부모 요소의 크기를 넘어설때
		- hidden : 넘어서는 부분 감추기
		- scroll : 넘어서는 부분 스크롤로 처리하기

- 유동 속성
	- float : 위치 지정
		해제는 clear : both 또는 부모 컨테이너에 overflow : hidden
		- left : 컴포넌트를 왼쪽부터 배치
		- right : 컴포넌트를 오른쪽부터 배치
	- clear : float의 영향을 지우는 속성
		- both : float이 left든 right든 적용

- 그림자 속성
	그림자를 중첩해서 여럿 줄 수도 있다. 이 경우 콤마로 연결한다.
	- text-shadow : (오른쪽) (아래) (흐림도) (색상)
	- box-shadow : (오른쪽) (아래) (흐림도) (색상)

- 생략표시
	text-overflow : ellipsis

- white-space : nowrap
	가로길이보다 글자가 많을 때 자동으로 줄이 바뀌는 것을 안 하도록 설정.
	이렇게 하면 글자가 넘칠 수 있다. 이때 text-overflow : ellipsis사용