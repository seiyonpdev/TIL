
- 형식
	select * 
	from 테이블명
	\[[[where]] 조건식\] 
	\[[[group by & having|group by]] 컬럼\] 
	\[having 조건식\]
	\[[[order by]] 컬럼\];
	ex.) select 컬럼... from 테이블명...  
	- select #distinct 컬럼명 from 테이블명;
		- 중복 제거된 결과를 볼 수 있다

- 실행순서
	select 컬럼명 **← 5**
	from 테이블명 **← 1**
	\[where 조건식\] **← 2**
	\[group by 컬럼명\] **← 3**
	\[having 조건식\] **← 4**
	\[order by 컬럼명\] **← 6**
