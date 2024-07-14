- 더 정확히는 PL/SQP (Procedural Language Structured Query Language)
- 오라클 전용 프로그래밍 언어
- PL/SQL로 만들 수 있는 것
	- [[프로시저|procedure]] : 자바의 메소드와 유사
	- function : select절에 사용할 수 있음
	- [[트리거|trigger]] : 이벤트(insert, update, delete가 발생하면 동작)

- 기본 구조
	declare
		변수명 자료형;
	begin
		프로시저호출(변수명);
		dbms.output.put_line(변수명)   ←콘솔에 출력하는 명령
	end;