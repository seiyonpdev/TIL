- select문으로 조회한 결과에 대하여 차례대로 행번호를 붙이기 위해 사용하는 속성
- order by랑 같이 쓸때는 정렬먼저 하고 행번호 붙이도록 서브쿼리 사용
	정렬한 결과에 대해 행번호를 붙여 앞에서부터 가져올 수는 있는데 
	중간만 잘라서 가져올 수는 없다. 그렇게 하려면 정렬한 것에 대하여 행번호 붙인것을
	다시 서브쿼리로 써야 한다.

- 형식
	ex.) select rownum, eno, ename
	from emp e, dept d
	where e.dno = d.dno
	and dname like '개발%';