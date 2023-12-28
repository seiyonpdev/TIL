- Asynchronous Javascript and XML
- DB로부터 데이터를 동적으로 가져오기 위해 자바스크립트로 서버에 데이터를 요청하는 기술

- 비동기적인 웹 애플리케이션의 제작을 위해 아래와 같은 조합을 이용하는 웹 개발 기법
	- 표현 정보를 위한 **HTML과 CSS**
	- 동적인 화면 출력 및 표시 정보와의 상호작용을 위한 **DOM, javascript**
	- 웹 서버와 비동기적으로 데이터를 교환하고 조작하기 위한 **XML, JSON**

- 사용자의 요청에 따라 서버로부터 데이터를 읽어오기 위한 방법이 Ajax이다.
	이때 다룰 서버의 기술은 [[jsp]], 서블릿, 스프링이다
	원래 서버의 프로그램인 jsp, 서블릿, 스프링은 동적인 html을 생성하는 것이 목적이지만
	Ajax통신으로 요청될 때에는 딱 **필요한 데이터만 응답**한다
		이때 데이터만 응답하는 방식으로는 csv, xml, **json**이 있다
			csv : Comma Seperate Value, 값을 컴마로 구분하여 응답하는 방식
			xml : Extensable Maskup Language, 값을 태그(mark)로 구분하여 응답하는 방식
			json : Javascript Object Notation, 값을 자바스크립트 객체의 형태로 응답

- 예시
	- csv ← 용량 작음, 의미 파악 어려움
		홍길동, 20, 서울
		이순신, 40, 대구
	- xml : 값의 의미를 알려주는 태그로 값을 락킹(Locking)한다 ← 용량 큼, 의미 파악 용이
		<\memberlist>
			<\member>
				<\name>홍길동<\/name>
				<\age>20<\/age>
				<\addr>서울<\/addr>
			<\/member>
			<\member>
				<\name>이순신<\/name>
				<\age>40<\/age>
				<\addr>대구<\/addr>
			<\/member>
		<\/memberlist>
	- json ← 용량 작음, 의미 파악 용이, 가장 많이 쓰임
		\[
			{name : "홍길동", age:20, addr:"서울"},
			{name : "이순신", age:40, addr:"대구"}
		\]
