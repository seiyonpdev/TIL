- 타입 호환 : 타입스크립트 코드에서 특정 타입과 다른 타입이 호환되는지를 의미한다

```typescript
interface Dog {
	name: string;
	age: number;
}

interface Cat {
	name: string;
	age: number;
}

interface Rabbit {
	name: string;
}

let i: Dog;
i = new Cat();

//C#이나 Java였다면 위 코드에서 에러가 났을 것이다.
//그러나 타입스크립트에서는 정상적으로 동작한다
//위 코드가 타입스크립트에서 정상 동작하는 이유는 자바스크립트의 작동 방식과 관계가 있다. 기본적으로 자바스크립트는 객체 리터럴이나 익명 함수 등을 사용하기 때문에 명시적으로 타입을 지정하는 것보다는 코드의 구조 관점에서 타입을 지정하는 것이 더 잘 어울린다

let bunny: Rabbit;
let kitty: Cat;
kitty = bunny;    //OK. Rabbit이 Cat보다 작기 때문에 가능
bunny = kitty;    //Error. Cat이 Rabbit보다 크기 때문에 불가능

//Enum 타입 호환
//Enum은 number 타입과 호환되지만 이넘 타입끼리는 호환되지 않는다
enum Status { Ready, Set, Go };
enum Color { Black, White, Green };

let status = Status.Ready;
status = Color.Green; //Error

//Class 타입 호환
//클래스 타입끼리 비교할 때 스태틱 멤버와 생성자를 제외하고 속성만 비교한다
class Tea {
	color: string;
	constructor(color: string, temperature: number) { }
}

class Coffee {
	color: string;
	constructor(color: string)
}

let a: Tea;
let b: Coffee;
a = b;  // OK
b = a;  // OK


//Generic 타입 호환
//제네릭 타입 간의 호환 여부를 판단할 때는 타입 인자 <T>가 속성에 할당됐는지를 기준으로 한다

interface Empty<T> { }
let x: Empty<number>;
let y: Empty<string>;

x = y;  // OK. 멤버 변수(=속성)가 없기 떄문에 같은 타입으로 간주한다

interface NotEmpty<T> {
	data: T;
}

let a: NotEmpty<number>;
let b: NotEmpty<string>;

a = b;  // Error. T가 data에 할당되었으므로 a와 b를 서로 다른 타입으로 간주한다.



```

#### 구조적 타이핑 (Structural Typing)
- 구조적 타이핑 : 코드 구조 관점에서 타입이 서로 호환되는지의 여부를 판단하는 것이다
- 위의 예시에서도 Dog와 Cat은 서로 다른 인터페이스지만 구조가 똑같기 때문에 서로 호환 가능하다.

