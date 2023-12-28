
- **where 절**에 사용할 수 있는 연산자
	1. 비교 : > , >=, <, <=, *=*, *<>*(not equal)
	2. 논리 : **and, or**
	3. 집합 : **in, not in**
		select bookname from book 
		**where publisher = '대한미디어' or publisher = '이상미디어';**
		위와 같은 결과를 출력하는 문장 ↓
		select bookname from book publisher **in ('이상미디어' , '대한미디어');**
		아닌 걸 조회할 때는 **not in**
	4. 범위 : **between, not between**
		select bookname from book where price **between** 10000 and 20000;
		**not between**은 그 반대 작용
	1. null : **is null, is not null**
	2. 패턴 : **like**
		문자열의 어떠한 패턴을 만족하는 데이터를 조회할 때 사용
		% : 모르는 0개 이상의 글자
		_ : 모르는 1개의 글자 
		ex.) 제목에 축구가 들어가는 모든 도서의 도서명을 출력
		select bookname from book where bookname like '%축구%';