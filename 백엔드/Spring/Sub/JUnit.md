
- 테스트 도구

- 메소드를 테스트해보고 싶은데 스프링으로 서버 켜고 난리법석 하고싶지 않을 때 src 폴더 아래에 test 폴더(=main과 형제)를 만들고 거기서 테스트한다
- src/test/java폴더 아래에 SimpleTest(이름은 뭐여도 상관 X)를 만들고 어노테이션으로 @Test를 붙인다
- 그런데 관례상 테스트 대상 클래스와 같은 경로의 패키지를 만들고 그 아래에 테스트 대상 클래스Test 라는 식으로 이름을 붙인다.
	- src/main/repository 아래의 MemberRepository를 테스트한다고 하면 테스트 케이스는 src/test/repository 아래에 MemberRepositoryTest 클래스 안에 만든다. 
- 테스트할 때는 해당 메소드에 우클릭 → Run As → JUnitTest