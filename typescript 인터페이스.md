
```typescript
//정의
interface Person {
	name: string,
	age: number
}

//변수에 인터페이스 활용
var jane: Person = {
	name: ‘Jane’,
	age: 10
}

//함수에 인터페이스 활용
function getPerson(person: Person) {
	console.log(person);
}
getPerson(jane);

//함수 구조를 정의하는 인터페이스
interface SumFunction {
	(a: number, b: number): number;
}
var sum: SumFunction;
sum = function(a: number, b: number): number{
	return a + b;
}

//인덱싱 방식을 정의하는 인터페이스














``` 