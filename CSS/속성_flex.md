- 현재 화면 배치를 할 때 가장 자주 사용되는 속성
- display에서 flex 혹은 inline-flex를 주고 디테일을 설정한다

- flex 컨테이너의 속성들
	- flex-direction : 요소를 배치하는 방향. justify-content, align-items, align-content에 영향을 준다
		- row : 행으로 배치, 디폴트
		- column : 열로 배치
		- row-reverse : 오른쪽부터 행으로 배치
		- column-reverse : 아래부터 열로 배치
	
	- justify-content : flex-direction의 메인 축에맞게 요소를 배치하는 형태
		- flex-start : flex-direction의 시작 지점에서부터 차례로 나열
		- center : 중앙 정렬
		- flex-end : flex-direction의 끝 지점에서부터 차례로 나열
		- space-between : 사이사이에 공간
		- space-around : 끝에도 감싸듯이 공간
		- space-evenly : 양 끝과 사이의 공간을 일정하게
	
	- align-content : flex-direction의 서브 축에맞게 요소를 배치하는 형태
		- justify-content와 속성값 종류가 동일
		- wrap으로 아이템이 여러 줄이 되면 사용
	
	- align-items : flex-direction의 서브 축에맞게 요소를 배치하는 형태
		- stretch : 꽉 채우게 늘려서 배치
		- flex-start
		- center
		- flex-end
	
	- flex-wrap : 자식 요소들이 부모 요소의 범위를 넘어갈 때 줄바꿈
		- nowrap : 줄바꿈 X
		- wrap : 줄바꿈 O
	
	- gap : 아이템 간의 간격
		- (세로) (가로)

- flex 컨테이너 안 아이템의 속성들
	- flex-basis : 메인 축상의 길이, 디폴트는 auto