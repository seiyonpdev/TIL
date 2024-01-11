- 현재 화면 배치를 할 때 가장 자주 사용되는 속성
- display에서 flex 혹은 inline-flex를 주고 디테일을 설정한다

- flex-direction : 요소를 배치하는 방향. justify-content, align-items, align-content에 영향을 준다
	- row : 행으로 배치
	- column : 열로 배치
	- row-reverse : 오른쪽부터 행으로 배치
	- column-reverse : 아래부터 열로 배치

- justify-content : x축 기준으로 요소를 배치하는 형태
	- flex-start : flex-direction의 시작 지점에서부터 차례로 나열
	- center : 중앙 정렬
	- flex-end : flex-direction의 끝 지점에서부터 차례로 나열
	- space-between : 사이사이에 공간
	- space-around : 끝에도 감싸듯이 공간
	- space-evenly : 양 끝과 사이의 공간을 일정하게

- align-items : y축 기준으로 요소를 배치하는 형태
	- stretch : 꽉 채우게 늘려서 배치
	- flex-start
	- center
	- flex-end

- flex-wrap : 
	- nowrap
	- wrap