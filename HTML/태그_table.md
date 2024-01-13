
- table : 표의 가장 겉면, 필수
	- border 속성으로 테두리 두께를 줄 수 있다
- tr : 한 행을 감싸는 태그
- th : 한 칸을 감싸는 태그. 강조되기 때문에 제목 등을 나타내는 데에 사용한다
	- scope 속성으로 col 혹은 row의 제목임을 나타낸
- td : 한 칸을 감싸는 태그
	- colspan : 칸을 합치는 속성. <\td colspan = "2">면 두 칸을 합친다. 합쳐진 칸은 지워준다
	- rowspan : 줄을 합치는 속성
- caption : 표 설명 또는 제목을 나타내는 태그, 선택사항

- thead : 테이블의 헤더, tbody 앞에 올 것
- tbody : 테이블의 본문
- tfoot : 테이블의 푸터, tbody 뒤에 올 것

- colgroup : 표의 열을 묶어서 속성 부여. table안, caption뒤, thead 앞
- col : 열의 묶음
	-  class 속성으로 묶을 단위의 이름을 준다
	- span 속성으로 묶을 범위를 지정한다