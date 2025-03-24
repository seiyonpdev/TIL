
- 이넘은 특정 값들의 집합을 의미하는 자료형이다. 
- 타입스크립트에서는 숫자형 이넘과 문자형 이넘을 지원한다

```typescript
//숫자형 이넘
//다음과 같이 숫자형 이넘을 선언할 때 초기값을 주면 초기값부터 차례로 1씩 증가한다
//초기값을 주지 않으면 0부터 차례로 1씩 증가한다 
enum Direction {
	Up = 1,
	Down,
	Left,
	Right
}

//숫자형 이넘 사용
function goWhere(person: string, direction: Direction): void{
//..
}
goWhere(‘Jamie’, Direction.Up);

//문자형 이넘
//숫자형 이넘과 거의 비슷하지만 런타임에서의 미세한 차이가 있다
//문자형 이넘은 이넘 값 전부 다 특정 문자 또는 다른 이넘 값으로 초기화 해줘야 한다
enum Direction {
	Up = ‘Up’,
	Down = ‘Down’,
	Left = ‘Left’,
	Right = ‘Right’
}

//문자형 이넘은 숫자형 이넘과 다르게 auto-incrementing이 없다
//대신 디버깅을 할 떄 숫자형 이넘의 값은 가끔 불명확하게 나올 때가 있지만 문자형 이넘은 항상 명확한 값이 나와 읽기 편하다

//복합 이넘(Heterogeneous Enums)
//기술적으로, 이넘에 문자와 숫자를 혼합하여 생성할 수 있다
//그러나 이 방식은 권고하지 않으며, 최대한 같은 타입으로 이뤄진 이넘을 사용하는 게 좋다
enum YesNo {
	Yes = ‘Yes’,
	No = 0
}
```

##### 런타임 시점에서의 이넘 특징
- 이넘은 런타임 시에 실제 객체 형태로 존재한다. 

```typescript
enum Variables {
	X, Y, Z
}

function getX(obj: { X:number }){
	return obj.X;
}

getX(Variables); //0
```

##### 컴파일 시점에서의 이넘 특징
- 이넘이 런타임 시점에서는 객체로 변환되지만 keyof를 사용할 때 주의해야 한다.
- 일반적으로 keyof를 사용해야 하는 상황에서는 대신 keyof typeof를 사용을 권장한다

##### 리버스 매핑
- **숫자형 이넘에만** 존재하는 특징이다
- 이넘의 키로 값을 얻을 수 있고 값으로 키를 얻을 수 있다

```typescript
enum Enum {
 A
}

let a = Enum.A; //키로 값을 획득하기
let keyName = Enum[a]; //값으로 키를 획득하기
```