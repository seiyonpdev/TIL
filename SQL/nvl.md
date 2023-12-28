- null value

- count는 조건을 만족하는 레코드가 없으면 0이 나온다.
	다른 집계함수는 레코드가 없으면 null이 나오기 때문에 nvl로 값을 대체해준다.

- 형식
	**nvl(컬럼 , 값*)**;
	컬럼의 값이 null이면 값에 지정된 값으로 대체해준다.
	ex. ) nvl(sum(o.saleprice), 0)