
 - 형식
	create table 테이블명
	(컬럼명1 데이터타입 \[제약조건\], 
	컬럼명2 데이터타입 \[제약조건\] ...);

- not null과 default 같이 쓸 때는 default가 먼저 와야 한다

- 기본키와 참조키의 설정
	1. 컬럼 단위의 설정 
		컬럼을 적어줄 때에 키를 설정
		- 형식
			- PK : bookid number primary key
			- FK : custid number references customer(custid)
	2. 테이블 단위의 설정
		컬럼들을 다 적고 맨 마지막에 키를 설정
		- 형식
			- PK : primary key(컬럼명1, \[컬럼명2\]...)
			- FK : foreign key(컬럼명) references 부모테이블(주식별자)

- 테이블 복사
	book테이블의 레코드를 모두 조회하여 동일한 칼럼과 레코드를 갖는 테이블 생성
	create table newbook **as select * from book**;

- 테이블 구조만 복사
	where 1 = 2는 절대로 만족하지 않는 조건. 
	따라서 레코드 제외하고 테이블 구조만 복사한 테이블 생성 
	create table newbook as select * from book **where 1 = 2**;