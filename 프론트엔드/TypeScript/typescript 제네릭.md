
 - 제네릭은 재사용성이 높은 컴포넌트를 만들 때 자주 활용되는 특징이다
 - 특히, 한가지 타입보다 여러가지 타입에서 동작하는 컴포넌트를 생성하는 데에 사용된다

```typescript
//파라미터와 반환값의 타입을 지정하지 않은 메서드
function getText(text) {
	return text;
}

getText(‘hi’); //hi
getText(10);   //10
getText(true); //true

//위 함수는 파라미터와 반환값의 타입을 지정하지 않아 any로 추론되었고 아무 타입이나 넣어서 아무 타입으로 나온다
//이 경우에는 함수 내부에서 특정 타입에서만 사용할 수 있는 메서드(예를 들면 string만 쓸 수 있는 split이라던가)를 호출할 수 없다

//제네릭을 사용한 메서드
//호출할 때 결정한 타입으로 메서드를 수행할 수 있다
function getText<T>(text: T): T {
	return text;
}

getText<string>(‘hi’);
getText<number>(10);
getText<boolean>(true);

//그런데 함수를 제네릭을 이용해서 정의했다면 호출할 때에 꼭 타입을 명시하지 않아도 알아서 어느정도 추론한다
const text getText<string>(‘eye of the tiger, a lion’);
//와의 text와 아래의 text는 사실상 같다
const text getText(‘eye of the tiger, a lion’);

//제네릭 인터페이스
interface Text<T> {
	(text: T): T;
}
interface Text {
	<T>(text: T): T;
}
function logText<T>(text:T): T {
	return text;
}
let str: Text<string> = logText;

//제네릭 클래스
class Math<T> {
	pi: T;
	sum: (x: T, y: T) => T;
}
let math = new Math<number>();


```


#### 제네릭 제약 조건
```typescript

```