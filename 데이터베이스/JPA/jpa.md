- Java Persistence API
- 백엔드에서 데이터베이스를 사용하는 프레임워크
- ORM (Object Relational Mapping) 제공
	- 객체와 DB의 데이터를 자동으로 맵핑시켜준다
	- ORM을 구현한 프레임워크의 이름이 Hibernate이다
	- 객체를 영속화하면 ORM이 DB에 저장하고 DB를 조회하면 ORM이 객체로 변환해서 돌려준다
	- ORM은 내부적으로 java 메소드에 적합한 SQL문을 자동으로 생성해서 실행한다

- 장점
	- 자바에서의 ORM을 위한 표준 인터페이스 제공
		- 이 표준을 따른 구현체가 Hibernate, EclipseLink, Apache Open JPA
	- 자동 매핑으로 개발 및 유지보수성 향상
	- 객체 지향적 접근 지원
	- DBMS에 독립적
		- DB 종류에 관계없이 JPA에서 자동으로 적합한 SQL Dialect를 만들어 주기 때문에 ==DB가 변경되어도 SQL문을 다시 작성할 필요가 없다==

- 단점
	- 높은 학습곡선 = 배우기 어렵다
	- 복잡한 SQL 생성의 어려움, SQL문 최적화 불가
		- 이 경우에는 직접 SQL을 작성하는 것이 낫기 때문이다

- jpa로 자동으로 쿼리를 만들 때 orderby 등의 조건을 추가하고 싶으면 메소드 명 뒤에 붙이면 된다
	- findByUserIdOrderByRegDdtsDesc(String userId) : 유저 아이디를 기준으로 조회, 등록일자 내림차순으로 정렬 