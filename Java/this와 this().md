- this
	- [[메소드]]의 매개변수 이름을 의미 있는 이름으로 정해 주다 보면
		[[속성]](멤버변수) 이름과 겹치게 됩니다
		메소드 안에서는 매개변수 이름이 우선순위가 높아서
		매개변수의 값을 다시 매개변수에 넣으라는 의미가 되고 
		속성의 값이 초기화 되지 않는다
	- 따라서 메소드의 매개변수 이름과 클래스의 멤버 자신을 구별할 목적으로 
		this를 사용한다
	- 형식
		this.name ← 클래스의 멤버변수 // 메소드의 매개변수는 그냥 name

- this()
	- [[생성자]]가 중복 정의되어 있을때에 생성자의 body안에서 다른 생성자를 요구할 때
		사용하는 키워드이다. 이 문장은 반드시 생성자의 첫번째 문장에 와야 한다.
