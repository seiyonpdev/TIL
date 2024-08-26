
- 타입 별칭 : 특정 타입이나 인터페이스를 참조할 수 있는 타입 변수를 의미한다
- 새로운 타입 값을 생성하는 것이 아니라 정의한 타입에 대해 나중에 쉽게 참고할 수 있게 이름을 부여하는 것이다
- 타입 별칭과 인터페이스의 가장 큰 차이점은 타입의 확장 가능 여부이다. 인터페이스는 확장이 가능한 반면 타입은 확장이 불가능하다. 따라서, 가능한 한 타입보다는 인터페이스로 선언하는 것을 권장한다

```typescript
type MyName = string;

type Developer = {
	name: string;
	skill: string;
}

type User<T> = {
	name: T
}

const name: MyName = ‘Olivia’;
const job: Developer = {
	name: ‘Backend Developer’;
	skill: Java;
}

```