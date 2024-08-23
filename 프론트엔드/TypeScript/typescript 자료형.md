```typescript
//string
let str: string = ‘hi’;

//number
let num: number = 3;

//boolean
let isLoggedIn: boolean = true;

//object
let user: object = { name: ‘Sophia’, age: 100 };
//객체 타입은 위와 같이 정의하는 것보다 인터페이스나 타입 별칭을 쓰는 게 낫다

//array
let arr: Array<number> = [1,2,3];
let arr: number[] = [1,2,3];

//tuple
//튜플은 배열의 길이가 고정되고 각 요소의 타입이 지정된 배열 형식을 말한다
//객체랑 배열 섞은거같이 생김
//만약 정의하지 않은 타입, 인덱스로 접근할 경우 오류가 난다
let arr: [string, number] = [‘hi’, 10];

//enum
enum Animal {
	Dog,
	Cat,
	Hamster
}
let kitty: Animal = Animal.Cat;
let micky: Animal = Animal[0];

//원한다면 이넘의 인덱스를 사용자 편의대로 변경하여 사용할 수도 있다
enum Season {
	Spring,
	Summer = 5,
	Fall,
	Winter
}
let thisSeason: Season = Season[5]; //Summer
let nextSeason: Season = Season[6]  //Fall

//any
//any타입은 모든 타입을 허용한다
//남용하면 타입스크립트의 장점이 사라지니까 꼭 필요할 때만 사용하자
let str: any = ‘hi’;
let num: any = 5;
let arr: any = [‘a’, 2, true];

//void
//반환 값이 없는 함수의 반환 타입. return이 없거나, return이 있더라도 반환하는 값이 없으면 함수의 반환 타입을 void로 지정
function printSomething(): void {
	console.log(‘sth’);
}
function returnNothing(): void {
	return;
}

//never
//절대 발생하지 않는 값을 의미하는 타입
//함수가 반복문이나 에러 핸들링으로 인해 함수의 끝에 절대 도달하지 않는 경우 사용
function loopForever(): never {
	while(true) {
		//..
	}
}
function neverEnd(): never {
	throw new Error(‘unexpected’);
}







```

- **:** 를 이용하여 자바스크립트 코드에 타입을 정의하는 방식을 타입 표기(Type Annotation)이라 한다.