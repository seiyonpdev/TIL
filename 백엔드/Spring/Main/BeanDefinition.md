
-  BeanDefinition : 스프링 빈 설정 메타 정보. 쉽게 이야기해서 **역할과 구현을 개념적으로 나눈 것**이다.
- 자바 코드(@Bean)를 읽든 XML(\<bean>)을 읽든 BeanDefinition을 만들 수 있으면 된다
- 스프링 컨테이너는 이 메타정보를 기반으로 스프링 빈을 생성한다
- 보통은 자바 코드로 만든 Config를 통해 알아서 만들어지지만 직접 생성해서 스프링 컨테이너에 등록할 수도 있다. 그런데 직접 생성할 일은 거의 없다.

#### 속성
- BeanClassName : 생성할 빈의 클래스명. 자바 설정처럼 팩토리 역할의 빈을 사용하면 없음.
- factoryBeanName : 팩토리 역할의 빈을 사용할 경우의 이름. (ex. appConfig) 
- factoryMethodName : 빈을 생성할 팩토리 메소드 지정 (ex. memberService)
- Scope : 싱글톤(기본값)
- lazyInit : 스프링 컨테이너를 생성할 때 빈을 생성하는 것이 아니라 실제 빈을 사용할 때까지 최대한 생성을 지연처리 하는지 여부
- InitMethodName : 빈을 생성하고, 의존관계를 적용한 뒤에 호출되는 초기화 메소드 명
- DestroyMethodName : 빈의 생명주기가 끝나서 제거하기 직전에 호출되는 메소드 명
- Constructor arguments, Properties : 의존관계 주입에서 사용한다. 자바 설정처럼 팩토리 역할의 빈을 사용하면 없음
