- input : 사용자로부터 입력을 받는 태그. 주로 form 안에 들어있다
- 타입 속성에 따라 다양한 형태로 입력을 받을 수 있다

- type
	- 텍스트 관련
		- text : 디폴트, 문자를 입력받는다
		- password : 비밀번호
		- search : 검색어 입력
		- tel : 전화번호
		- 텍스트 관련 인풋 속성들
			- placeholder : 빈 칸에 보이는 안내문
			- maxlength : 최대 길이
			- minlength : 최소 길이
	- 숫자 관련
		- number : 숫자
		- range : 게이지 바
		- date : 날짜
		- 숫자 관련 인풋 속성들
			- max : 최대값
			- min : 최소값
			- step : 간격 (range 등에서 사용)
	- 체크 관련
		- checkbox : 체크박스
		- radio : 라디오버튼
		- 체크 관련 인풋 속성들
			- checked : disabled처럼 값 없이 단독 사용, 체크됨
			- name : 옵션들을 그룹지어줄 때 사용
			- value : 각 옵션의 실제로 넘겨지는 값
	- 기타
		- file : 파일 선택
		- 파일 인풋 속성들
			- accept : 받아들일 수 있는 파일 형식
			- multiple : 값 없이 단독 사용, 여러 파일 업로드 가능 여부
		- email : 이메일
		- url : url 주소
		- **hidden** : 굳이 사용자에게 입력받을 필요는 없지만 다른 정보들과 함께 전송해야 하는 내용을 히든으로 보낸다

- 공통으로 사용 가능한 속성들
	- value : 입력 칸에 디폴트 값을 지정할 수 있다
	- autofocus : 값 없이 단독 사용, 입력만 하면 되게끔 자동으로 미리 포커스를 맞춰준다
	- readonly : 값 없이 단독 사용, 값을 수정할 수 없고 읽기만 가능, 값이 전송됨
	- required : 값 없이 단독 사용, 필수 입력
	- disabled : 값 없이 단독 사용, 비활성화, 전송 안됨

- 특정 태그에서 눈여겨 볼 속성들
	- multiple : select태그의 속성. 다중 선택 가능
	- selected : option태그의 속성. 선택됨
	- value : option태그의 속성. 실제로 전송될 값
	- list : input태그의 속성. 연결할 datalist의 아이디를 준다

- input 태그는 아닌데 입력받는 태그
- textarea : 텍스트를 입력하는 넓은 칸, **기본값을 value로 주지 않고 태그 안에 입력!**
	- 속성
		- cols : 글자수 단위의 너비, 디폴트 20
		- rows : 칸의 줄 수
- select : 디폴트 콤보박스
	- option : select태그 내부의 옵션 태그에 항목을 적는다
	- optgroup : optgroup으로 같은 카테고리의 option을 묶어서 표현할 수 있다
		- optgroup의 속성
			- label : optgroup의 이름
	- select의 속성
		- size : 1 이상 주면 리스트로 바뀐다
- datalist : 이 태그의 id를 input태그의 list에 줘서 datalist를 만든다
	- option : datalist태그 내부의 옵션 태그에 항목을 적는다

