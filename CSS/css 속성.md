- [[속성_박스|박스 속성]]
- [[속성_가시 속성|가시 속성]]
- [[속성_배경|배경 속성]]
- [[속성_글자와 텍스트|글자 속성]]

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
		- 위아래 좌우를 따로 값을 줄 수도 있다
			- (위아래) (좌우)
			- overflow : scroll hidden으로 주면 위아래는 scroll이 생기고 좌우는 안 보인다

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