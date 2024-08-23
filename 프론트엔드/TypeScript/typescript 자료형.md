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
let nextSeason: Season = Season[6]










```

- **:** 를 이용하여 자바스크립트 코드에 타입을 정의하는 방식을 타입 표기(Type Annotation)이라 한다.