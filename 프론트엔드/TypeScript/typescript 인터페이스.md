
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
interface StringArray {
	[index: number]: string;
}

var arr: StringArray = [‘red’, ‘blue’, ‘green’];
arr[1]; //blue

//딕셔너리 패턴
interface StringRegexDictionary {
	[key: string]: RegExp;
}

var obj: StringRegexDictionary = {
	cssFile: /\.css$/,
	jsFile: /\.js$/,
}

//키를 가지고 배열을 순회하기
Object.key(obj).forEach(function(value){
	//..
})

//상속
interface Student extends Person{
	major: string;
}

var lily: Student = {
	major: ‘Computer Science’,
	name: ‘Lily’,
	age: 22
}

//옵션 속성
interface Bird {
	flyable?: boolean;
}

//읽기 전용 속성
//처음 생성할 때만 값을 할당하고 그 이후에는 변경 불가. 읽기만 가능하다.
interface TeamColor {
	readOnly color: string;
}

//미리 정의하지 않은 속성 사용
interface CraftBeer {
	brand?: string;
	[propName: string]: any;
}

//클래스 타입
//자바에서 쓰듯이 클래스의 설계도로 기능하도록 사용
interface CraftBeer {
	beerName: string;
	nameBeer(beer: string): void;
}

class myBeer implements CraftBeer {
	beerName: string = ‘Honeydew’;
	nameBeer(b: string) {
		this.beerName = b;
	}
	constructor() {}
}



``` 