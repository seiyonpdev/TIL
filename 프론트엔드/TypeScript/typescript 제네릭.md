
 - 제네릭은 재사용성이 높은 컴포넌트를 만들 때 자주 활용되는 특징이다
 - 특히, 한가지 타입보다 여러가지 타입에서 동작하는 컴포넌트를 생성하는 데에 사용된다

```typescript
//파라미터와 반환값의 타입을 지정하지 않은 메서드
function getText(text) {
	return text;
}

getText(‘hi’); //hi
getText(10);   //10
getText(true); //
```