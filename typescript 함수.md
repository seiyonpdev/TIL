
- 타입스크립트에서 주로 함수를 정의하는 3가지 타입
	1. 매개변수 타입
	2. 반환 타입
	3. 구조 타입

```typescript
//함수의 기본적인 타입 선언
function sum(a: number, b: number): number {
	return a + b;
}

//옵셔널 파라미터
//타입스크립트에서는 함수의 인자를 모두 필수 값으로 간주한다. 그래서 함수를 실제로 사용할 때, 미리 정의한 파라미터를 모자라지도 넘치지도 않게 담아서 보내야 한다.
//이런 특성은 정의된 매개변수의 갯수만큼 인자를 넘기든 말든 별 상관 없는 유연한 자바스크립트의 특성과 반대된다. 
//이때 옵셔널 파라미터를 사용해서 파라미터를 넘길 수도 안 넘길 수도 있게 정의할 수 있다.
//파라미터 이름 뒤에 물음표를 붙이면 옵셔널 파라미터가 된다
function sum(a: number, b?: number): number {
	return a + b;
}

//매개변수 초기화
function sum(a: number, b = ‘100’): number {
	return a + b;
}
sum(10, undefined);  //110
sum(10);             //110
sum(10, 20, 30);     //error, too many parameters

//스프레드 연산자
function sum(a: number, …nums: number[]): number {
	let totalNums = 0;
	for (let key of nums) {
		totalNums += num;
	}
	return a + totalNums;
}





```