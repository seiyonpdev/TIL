
#### Union Type

- Union Type : 자바스크립트의 OR 연산자(||)와 같이 A이거나 B이다라는 의미의 타입이다

```typescript
function logText(text: string | number){
//..
}
```

- 위 함수의 파라미터 text에는 문자열 타입이나 숫자 타입이 모두 올 수 있다. 이처럼 | 연산자를 이용하여 타입을 여러 개 연결하는 방식을 유니온 타입 정의 방식이라고 한다

##### Union Type의 장점
- 위의 예시에서 text의 타입으로 any를 사용하면 숫자 관련된 API를 적용할 수 없다. 반면 유니온 타입을 사용하면 숫자, 문자열 관련된 API를 적용할 수 있다.
- any를 사용하면 자바스크립트로 작성하는 것처럼 동작하고, 유니온 타입을 사용하면 타입스크립트의 장점을 살리면서 코딩할 수 있다

##### Union Type 사용 시 주의점
```typescript
interface Person {
	name: string;
	age: number;
}
interface Student {
	name: string;
	major: string;
}

function introduce(someone: Person | Student){
	someone.name; //O 정상 동작
	someone.age;  //X 타입 오류
	someone.skill;//X 타입 오류
}
```

- 타입스크립트 관점에서는 introduce() 호출 시점에 Person 타입이 올지 Student 타입이 올지 알 수 없기 떄문에 어떤 타입이 들어와도 오류가 안 나는 방향으로 타입을 추론한다.
- introduce() 함수 안에서 별도의 [[typescript 타입 가드|타입 가드]]를 이용하여 타입의 범위를 좁히지 않는 한 두 타입에 공통적으로 들어있는 속성인 name에만 접근할 수 있다

#### Intersection Type
- Intersection Type : 여러 타입을 모두 만족하는 하나의 타입을 의미한다
```typescript
interface Person {
	name: string;
	age: number;
}
interface Student {
	name: string;
	major: string;
}
type Alice = Person & Student;

//결과적으로 Alice 타입은 다음과 같이 정의된다
{
	name: string;
	age: number;
	major: string;
}
```

