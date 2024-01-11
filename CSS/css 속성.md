- [[속성_박스|박스]]
- [[속성_가시 속성|가시 속성]]
- [[속성_배경|배경]]
- [[속성_글자와 텍스트|글자]]
- [[속성_위치|위치]]
- [[속성_커서|커서]]
- 

- 유동 속성
	- float : 위치 지정
		해제는 clear : both 또는 부모 컨테이너에 overflow : hidden
		- left : 컴포넌트를 왼쪽부터 배치
		- right : 컴포넌트를 오른쪽부터 배치
	- clear : float의 영향을 지우는 속성
		- both : float이 left든 right든 적용

- 생략표시
	text-overflow : ellipsis

- white-space : nowrap
	가로길이보다 글자가 많을 때 자동으로 줄이 바뀌는 것을 안 하도록 설정.
	이렇게 하면 글자가 넘칠 수 있다. 이때 text-overflow : ellipsis사용