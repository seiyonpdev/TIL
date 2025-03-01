
- 테스트 도구
- TDD(Test Driven Development) : 테스트 틀을 먼저 만들고 그 테스트를 통과하도록 개발을 진행하는 방식.

- 메소드를 테스트해보고 싶은데 스프링으로 서버 켜고 난리법석 하고싶지 않을 때 src 폴더 아래에 test 폴더(=main과 형제)를 만들고 거기서 테스트한다

- src/test/java폴더 아래에 SimpleTest(이름은 뭐여도 상관 X)를 만들고 어노테이션으로 @Test를 붙인다

- 그런데 관례상 테스트 대상 클래스와 같은 경로의 패키지를 만들고 그 아래에 테스트 대상 클래스Test 라는 식으로 이름을 붙인다.
	- src/main/repository 아래의 MemberRepository를 테스트한다고 하면 테스트 케이스는 src/test/repository 아래에 MemberRepositoryTest 클래스 안에 만든다. 


#### 용례
- print문을 찍어보고 싶으면 println 대신 Assert를 사용하자

1. org.junit.jupiter.api의 Assertions를 사용하는 경우
	- Assertions.**assertEquals**(actual, expected);
		- 이렇게 하면 input과 searchTarget이 같은지 확인할 수 있다
2. org.assertj.core.api의 Assertions를 사용하는 경우
	- Assertions.**assertThat**(actual).isEqualTo(expected);

- **assertThrow** : 발생해야 하는 예외가 잘 발생하는지 확인할 수 있다

- same과 equal의 의미가 다르다
	- same : 두 객체의 메모리 주소를 비교해서 **동일한 레퍼런스를 참조**하는지 확인한다
	- equal : 두 객체의 값을 비교한다. 서로 다른 객체여도 그 안의 값이 같으면 같다고 판단한다

- Assertj가 더 쓰기 편한 관계로 더 흔히 쓰인다

- Assert로 테스트를 하면 프린트문이 찍혀서 나오지는 않는다. 그러나 예상외의 결과가 나오면 빨간 오류메시지로 알려 준다. 즉 Assert가 초록색으로 문제없이 지나갔다면 통과.

#### 실행

- 테스트할 때는 해당 메소드에 우클릭 → Run As → JUnitTest
- 아니면 클래스 전체를 돌릴 수도 있다. 이 경우 테스트하는 메소드의 순서는 보장되지 않기 때문에, **각 테스트가 개별적으로 동작하도록 만들어야 한다**. 그러지 않으면 앞선 테스트 메소드에서 저장한 데이터를 뒤의 테스트 메소드가 읽어버리면서 의도하지 않은 혼선이 생긴다.
- 이런 경우를 방지하고자 하나의 테스트 메소드가 끝날 때마다 레포지토리를 clear하도록 설정할 수 있다.
- 아래와 같이 @AfterEach 어노테이션을 붙인 메소드는 테스트를 돌릴 때 테스트 메소드 하나가 끝날때마다 작동한다. 그러니까 청소기.
```java
@AfterEach
public void afterEach() {
	store.clearStore();
}
```
