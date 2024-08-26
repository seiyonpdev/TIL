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

	constructor(name: string, age: number, readonly log: string) {
		this.name = name;
		this.age = age;
		this.log = log;
	}
}


```
