- 자바스크립트의 프로토타입 기능을 객체지향 언어에 익숙한 사람들이 사용하기 쉽게끔 클래스라는 형태로 제공한다
- 그러나 형태만 클래스일 뿐 실제로는 프로토타입 기반으로 작동한다

#### 클래스
- 클래스의 속성에 접근제어자를 사용할 수 있다
- readonly의 경우 읽기만 가능하고 수정할 수 없다
- readonly를 사용하면 constructor() 함수에 초기 값 설정 로직을 넣어줘야 하므로 다음과 같이 인자에 readonly 키워드를 추가해서 코드를 줄일 수 있다

```typescript
class Person {
	private name: string;
	public age: number;
	readonly log: string;

	get name(): string {
		return this.name;
	}

	set name(newValue: string) {
		if(newValue && newValue.length > 5) {
			throw new Error(‘이름이 너무 깁니다’);
		} 
		this.name = newValue;
	}

	constructor(name: string, age: number, readonly log: string) {
		this.name = name;
		this.age = age;
		this.log = log;
	}
}

const jack = new Person();
jack.name = ‘Jack Jackson’;  //Error
jack.name = ‘Jack’;

//get만 선언하고 set을 선언하지 않는 경우에는 자동으로 readonly로 인식됩니다

```

#### 추상 클래스
- 추상 클래스는 인터페이스와 비슷한 역할을 하면서도 조금 다르다
- 추상 클래스는 특정 클래스의 상속 대상이 되는 클래스이며 좀 더 상위 레벨에서 속성, 메서드의 모양을 정의한다
- 추상 클래스는 구현한 메서드와 시그니처만 있는 메서드를 둘 다 가질 수 있다
- 추상 클래스를 상속받는 클래스는 추상 클래스에 시그니처만 정의된 메서드를 **반드시 구현**해야 한다
