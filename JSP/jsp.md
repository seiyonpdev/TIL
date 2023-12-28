- Java Server Page

- **웹 프로그래밍** 언어
- Server side에서 동작. 소스코드가 노출되지 않는다
- 기본 웹 프레임워크의 한 종류
- HTML 사이에 스크립트 언어 형식으로 Java 기반하여 프로그램 작성
- jsp로 요청하면 톰캣이 그걸 서블릿으로 만들어주어서 실행한다

- **동적**인 문서
- 서버 측에서 실행된다
- html + 자바 문법

<% %> ← 이거(스트립트릿) 쓰고 이 안에 자바 문법으로 동적인 처리를 해준다
<%= %> ← 자바에서 가져온 것을 출력하는 태그. 표현식이라 부른다
	ex.) <%= rs.getInt(1)%>
<%@ ← import할때 전처리하는 기호, 이름은 지시자

jsp문서에서 사용자가 입력한 값 받아오기
	[[request]].getParameter("이름");
	이 값을 한글로 받아오려면 먼저 인코딩부터 설정한다
	[[request]].setCharacterEncoding("UTF-8");

insert를 자바의 String sql 로 쓸 때는 values에 넣을 값을 ?로 대신할 수 있다
ex.)String sql = "insert into book values(?, ?, ?, ?)"
이걸 적용하려면 Statement대신 PreparedStatement를 쓴다
그리고 꼭 pstmt.setInt나 setString으로 ?에 값을 설정해준다.