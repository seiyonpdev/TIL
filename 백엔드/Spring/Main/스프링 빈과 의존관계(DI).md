
- Dependency Injection(DI) : 의존성 주입. 서비스 클래스, 레포지토리 등 매번 객체를 생성할 이유가 없는 경우 **하나의 객체를 공유**하도록 **외부에서 주입**해주는 것을 말한다

- 스프링 빈 : 컨트롤러, 서비스, 레포지토리 등 여러번 객체를 생성할 필요 없이 공유할 수 있도록 스프링 컨테이너에서 관리하는 **하나의 객체**를 스프링 빈이라고 한다

#### 스프링 빈을 등록하는 방법 2가지
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

#### 의존성을 주입하는 방법 3가지
1. Field Injection
	- 클래스의 멤버 변수에 Injection 관련 어노테이션(@Autowired)를 선언
	- 가장 편하지만 필드 객체를 수정할 수 없으므로 왠만하면 사용하지 말 것
2. Setter Injection
	- 클래스의 멤버 변수로 선언된 객체에 대하여 Injection 하는 방식
	- 내부적으로 setter를 사용하여 주입
	- **선택**, **변경** 가능성이 있는 의존관계에 사용
	- *참고* : @Autowired의 기본 동작은 주입할 대상이 없으면 오류가 발생한다. 주입할 대상이 없어도 동작하게 하려면 `@Autowired(required = false)`로 지정하면 된다
1. Construct Injection
	- 클래스 생성 시 의존관계를 Injection하는 방식
	- 클래스 생성 시 한 번 호출되므로 주입받는 객체가 변하지 않거나, 반드시 객체의 주입이 필요한 경우를 강제할 수 있다
	- 클래스 생성 시 주입되는 Bean이 생성되므로, 어플리케이션 기동 시 오류 여부를 확인할 수 있고, 순환 참조를 사전에 방지할 수 있다
	- **불변**하고, **필수**적인 의존관계에 사용한다
	- 생성자가 딱 **1개 있으면 @Autowired를 생략해도 자동 주입**된다. 물론 스프링 빈에만 해당한다
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


#### 의존관계의 종류
1. 정적인 클래스 의존관계
	- 클래스가 사용하는 import 코드만 보고 의존관계를 쉽게 판단할 수 있다.
	- 정적인 의존관계는 애플리케이션을 실행하지 않아도 분석할 수 있다. 
	- IntelliJ에는 정적인 의존관계 다이어그램을 보여주는 기능이 있다. 분석하려는 패키지 우클릭 - Show Diagram, 다이어그램 우클릭 - Show Dependency
2. 실행 시점에 결정되는 동적인 객체(인스턴스) 의존 관계
	- 애플리케이션 실행 시점(런타임)에 외부에서 실제 구현 객체를 생성하고 클라이언트에 전달해서 클라이언트와 서버의 실제 의존관계가 연결되는 것을 의존관계 주입이라 한다
	- 객체 인스턴스를 생성하고, 그 참조값을 전달해서 연결된다
	- 의존관계 주입을 사용하면 클라이언트 코드를 변경하지 않고, 클라이언트가 호출하는 대상의 타입 인스턴스를 변경할 수 있다
	- 의존관계 주입을 사용하면 정적인 클래스 의존관계를 변경하지 않고, 동적인 객체 인스턴스 의존관계를 쉽게 변경할 수 있다

#### 옵션 처리
- 주입할 스프링 빈이 없어도 동작해야 할 때가 있다. 그런데 `@Autowired`만 사용하면 `required` 옵션의 기본값이 `true`로 되어 있어서 자동 주입 대상이 없으면 오류가 발생한다
- 자동 주입 대상을 옵션으로 처리하는 방법
	- `@Autowired(required=false)` : 자동 주입할 대상이 없으면 수정자 메서드 자체가 호출 안됨
	- `org.springframework.lang.@Nullable` : 자동 주입할 대상이 없으면 null이 입력된다
	- `Optional<>` : 자동 주입할 대상이 없으면 `Optional.empty`가 입력된다

#### 권장 : 생성자 주입
- 과거에는 수정자 주입과 필드 주입을 많이 사용했지만 최근에는 스프링을 포함한 DI 프레임워크 대부분이 생성자 주입을 권장한다. 그 이유는 아래와 같다

##### 불변
- 대부분의 의존관계 주입은 한 번 일어나면 애플리케이션 종료시점까지 의존관계를 변경할 일이 없다. 오히려 대부분의 의존관계는 애플리케이션 종료 전까지 불변해야 한다
- 수정자 주입을 사용하면 setter 메소드를 public으로 열어둬야 한다
- 누군가 실수로 변경할 수도 있고, 변경하면 안되는 메소드를 열어두는 것은 좋은 설계 방법이 아니다
- 생성자 주입은 객체를 생성할 때 딱 1번만 호출되므로 이후에 호출되는 일이 없어서 불변하게 설계할 수 있다

##### 누락
- 프레임워크 없이 순수 자바 코드를 단위 테스트 하는 경우에 수정자 주입을 사용하면 의존관계 주입이 누락되어 Null Point Exception이 발생한다
- 생성자 주입을 사용하면 이처럼 주입 데이터를 누락했을때 컴파일 오류가 발생하여 어떤 값을 필수로 주입해야 하는지 알려준다

##### final 키워드
- 생성자 주입을 하면 final 키워드를 쓸 수 있다. 생성자에서 혹시라도 값이 설정되지 않는 오류가 생기면 컴파일 시점에 막아준다. 이렇게 하면 생성 후에 불변함을 더 단단하게 보장한다

##### 결론
- 생성자 주입 방식을 사용하면 프레임워크에 의존하지 않고 순순한 자바 언어의 특징을 잘 살릴 수 있다
- 기본적으로 생성자 주입을 사용하고 필수 값이 아닌 경우에는 수정자 주입 방식을 옵션으로 부여하면 된다. 생성자 주입과 수정자 주입을 동시에 사용할 수 있다
- **항상 생성자 주입을 선택하라**. 그리고 가끔 옵션이 필요하면 수정자 주입을 선택해도 좋다. 필드 주입은 사용하지 마라