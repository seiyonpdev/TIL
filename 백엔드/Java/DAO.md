- 조회할때는 stmt.executeQuery(sql) 해서 결과를 ResultSet으로 받아온다.
- 조회한 칼럼만 ResultSet에 나오기 때문에 고려해서 rs.get~()할 것
	while(rs.next()){
		**//ResultSet의 첫번째에 있을 문자열 받아오기**
		rs.getString(1);
		**//ResultSet의 두번째에 있을 정수 받아오기**
		rs.getInt(2);
	}

- insert 메소드 형식
String sql = "insert into student values('' + name + "'," + kor + "," + eng + "," + math + "," + tot + "," + avg + ")";
try {
	**//1. JDBC 드라이버를 메모리로 로드한다**
	Class.forName("oracle.jdbc.driver.OracleDriver");
	**//2. DB 서버에 연결한다**
	Connection conn = DriverManager.getConnection("jdbc:oracle:thin:@localhose:1521:XE");
	*localhost는 자기 자신을 지칭한다. 다른 컴퓨터에 접속할때는 다른 컴퓨터의 IP를 넣는다*
	**//3. 커넥션 객체를 통해서 DB 명령을 실행하기 위한 Statement 객체를 생성한다**
	Statement stmt = conn.createStatement();
	**//4. Statement 객체를 통해서 DB 명령을 실행한다**
	int re = stmt.executeUpdate(sql);
	*행을 추가한 수만큼 정수를 반환, 실패시 0을 반환한다*
	if(re == 1){
	성공
	}else {
	실패
	}
	**//5. 사용했던 자원을 닫아 준다**
	stmt.close();
	conn.close();
}catch(Exception e) {

}
