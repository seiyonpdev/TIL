
- 타입 가드 : 여러 개의 타입 중 하나의 타입으로 타입을 좁히는 것을 말한다
- 타입 가드 연산자 : typeof, instanceof

```typescript
//커스텀 타입 가드 함수
function isString(age: string | number): age is string {
	return typeof age === ‘string’;
}

function getAge(age: string | number) {
	if(isString(age)) {
		age.length;
	}
}
```