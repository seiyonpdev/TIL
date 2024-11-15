
- 테스트 도구

- 메소드를 테스트해보고 싶은데 스프링으로 서버 켜고 난리법석 하고싶지 않을 때 src 폴더 아래에 test 폴더(=main과 형제)를 만들고 거기서 테스트한다

- src/test/java폴더 아래에 SimpleTest(이름은 뭐여도 상관 X)를 만들고 어노테이션으로 @Test를 붙인다

- 그런데 관례상 테스트 대상 클래스와 같은 경로의 패키지를 만들고 그 아래에 테스트 대상 클래스Test 라는 식으로 이름을 붙인다.
	- src/main/repository 아래의 MemberRepository를 테스트한다고 하면 테스트 케이스는 src/test/repository 아래에 MemberRepositoryTest 클래스 안에 만든다. 

- print문을 찍어보고 싶으면 println 대신 Assert를 사용하자

1. org.junit.jupiter.api의 Assertions를 사용하는 경우
	- Assertions.assertEquals(expected, actual);
		- 이렇게 하면 input과 searchTarget이 같은지 확인할 수 있다
2. org.assertj.core.api의 a


- Assert로 테스트를 하면 프린트문이 찍혀서 나오지는 않는다. 그러나 예상외의 결과가 나오면 빨간 오류메시지로 알려 준다. 즉 Assert가 초록색으로 문제없이 지나갔다면 통과.

- 테스트할 때는 해당 메소드에 우클릭 → Run As → JUnitTest

