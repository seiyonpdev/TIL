
1. 순수 JDBC
	- DB랑 Spring 사이에 흐르는 강을…나무 사다리를 다리삼아 건너는 느낌
	- DB의 겉면에 최소한의 처리를 해서 Spring이 지껄이는 소리를 알아듣게 만든다…
2. 스프링 JDBC Template
	- JDBC를 좀 더 편하게 써볼려고 만든 장치
	- 조금 편해지기는 하는데 나무사다리를 철 사다리로 업그레이드한 느낌
3. JPA
	- SQL을 직접 쓸 필요가 없도록 발전했다
	- 그러나 몇몇 쿼리는 JPQL이라는 형태로 직접 써줘야 한다
4. 스프링 데이터 JPA
	- SQL을 더더욱 직접 쓸 필요가 없어졌다.(JPQL 멸종)
	- 그래도 복잡한 쿼리는 다른 방법으로 사용한다. 이를테면 QueryDSL
	- 직접 쿼리를 적을 수 있는 방법도 열려있다. JDBC Template과 혼용 가능

- JPA와 MyBatis 혼용 가능( +JDBC Template도)