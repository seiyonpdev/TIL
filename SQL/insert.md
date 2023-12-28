- [[select]] 한 결과를 insert 하기
	insert into 테이블명 select ~

- insert into 테이블명 values(값1 , 값2...);
	처음에 설정한 컬럼 순서대로

- insert into 테이블명(컬럼명 1, 컬럼명 2...) values(값1, 값2...); 
	- 나열한 컬럼명 순서대로 values 넣을 수 있는 명령문
	- 나열된 컬럼 이외의 컬럼들은 null이거나 default가 있어야 한다.