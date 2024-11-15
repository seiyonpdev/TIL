
- Dependency Injection(DI) : 의존성 주입. 서비스 클래스, 레포지토리 등 매번 객체를 생성할 이유가 없는 경우 **하나의 객체를 공유**하도록 **외부에서 주입**해주는 것을 말한다

- 스프링 빈 : 컨트롤러, 서비스, 레포지토리 등 여러번 객체를 생성할 필요 없이 공유할 수 있도록 스프링 컨테이너에서 관리하는 **하나의 객체**를 스프링 빈이라고 한다

- 스프링 빈을 등록하는 방법 2가지
	1. 컴포넌트 스캔과 자동 의존관계 설정
		- @Controller, @Service, @Repository 등으로 컴포넌트라고 적시해두면 스프링 컨테이너가 해당 클래스를 스캔해서 빈을 만든다
		- SpringAppApplication이 있는 패키지 내의 컴포넌트만 스캔하니 주의
	2. 자바 코드로 직접 스프링 빈 등록하기
		1. SpringAppApplication이 있는 위치에 SpringConfig(이름 자유)라는 클래스를 생성
		2. 해당 클래스에 @Configuration 어노테이션을 붙인다
		3. 클래스 내부에 다음 예시코드와 같이 직접 스프링 빈을 등록한다
```java
@Bean
public MemberService memberService() {
	return new MemberService();
}
```

- 의존성을 주입하는 방법 3가지
	1. Field Injection
		- 클래스의 멤버 변수에 Injection 관련 어노테이션(@Autowired)를 선언
		- 가장 편하지만 필드 객체를 수정할 수 없으므로 왠만하면 사용하지 말 것
	2. Setter Injection
		- 클래스의 멤버 변수로 선언된 객체에 대하여 Injection 하는 방식
		- 내부적으로 setter를 사용하여 주입
	3. Construct Injection
		- 클래스 생성 시 의존관계를 Injection하는 방식
		- 클래스 생성 시 한 번 호출되므로 주입받는 객체가 변하지 않거나, 반드시 객체의 주입이 필요한 경우를 강제할 수 있다
		- 클래스 생성 시 주입되는 Bean이 생성되므로, 어플리케이션 기동 시 오류 여부를 확인할 수 있고, 순환 참조를 사전에 방지할 수 있다
```java
//Field Injection
public class MemberController {
	@Autowired
	private MemberService memberService;
}

//Setter Injection
public class MemberController {
	private MemberService memberService;

	@Autowired
	public void setMemberService(MemberService service){
	this.memberService = service;
	}
}
//Construct Injection
@Service
@RequiredArgsConstructor
public class MemberController {
	private final MemberService memberService;
}

```