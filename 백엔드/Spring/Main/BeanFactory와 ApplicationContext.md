
- BeanFactory 인터페이스 -상속→ ApplicationContext 인터페이스 -상속→ AnnotationConfigApplicationContext 클래스
- BeanFactory를 직접 사용할 일은 거의 없으며, 주로 ApplicationContext를 사용한다. 둘 다 스프링 컨테이너라고 본다

#### BeanFactory
- 스프링 컨테이너의 최상위 인터페이스
- 스프링 빈을 관리하고 조회(getBean() 등…)하는 역할을 담당

#### ApplicationContext
- BeanFactory를 상속받았으니 당연히 상속받은 인터페이스의 모든 기능 제공
##### ApplicationContext가 제공하는 부가가능
- MessageSource 인터페이스 : 메시지소스를 활용한 국제화 기능. 한국에서 들어오면 한국어로, 영어권에서 들어오면 영어로 출력
- EnvironmentCapable 인터페이스 : 로컬, 개발, 운영 등을 구분해서 처리
- ApplicationEventPublisher 인터페이스 : 이벤트를 발행하고 구독하는 모델을 편리하게 지원
- ResourceLoader 인터페이스 : 파일, 클래스패스, 외부 등에서 리소스를 편리하게 조회
