- form : 입력 양식을 가장 겉에서 감싸주는 태그. 받은 정보를 서버로 보내려면 필요.
	- action = "제출받아서 작동할 웹 페이지"
	- method = "전송 방식
		get 과 post 방식이 있는데 get은 내용이 노출되고 post는 그렇지 않아서
		주로 post를 사용한다. 디폴트는 get.
	- autocomplete : 디폴트 on. off로 설정하면 자동완성을 하지 않는다

- fieldset : form 태그 내 입력요소와 라벨들을 그룹화
	- disabled 속성으로 포함된 입력요소 비활성화

- legend : fieldset요소의 제목

- label : input태그의 이름을 표시해주는 역할
	- for 속성에 짝이 되는 input태그의 id를 준다

- button : 버튼을 만든다
	- type속성에 
		- submit을 주면 form의 action 링크로 제출
		- reset을 주면 초기화 기능
		- button을 주면 java script등으로 다른 기능을 부여할 수 있는 맨 버튼

- [[태그_input|input]]
