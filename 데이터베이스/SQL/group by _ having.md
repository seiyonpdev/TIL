
- 그룹별 집계 함수
	- **group by(컬럼명)**
		~별로 집계하기, *이때는 일반 조회문과 함께 사용 가능*
		ex.) 출판사 별로 도서의 평균 금액 내기
	- **having**
		group by절의 결과에 대해 조건식을 주고 싶을때
		ex.)
		select bookname, count(\*)from book b, orders o
		where b.bookid = o.bookid
		and publisher in ('대한미디어', '이상미디어')
		group by bookname
		**having count(\*) >= 2**
		order by count(\*) desc;