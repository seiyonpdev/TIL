
#### Union Type

- Union Type : 자바스크립트의 OR 연산자(||)와 같이 A이거나 B이다라는 의미의 타입이다

```typescript
function logText(text: string | number){
//..
}
```

- 위 함수의 파라미터 text에는 문자열 타입이나 숫자 타입이 모두 올 수 있다. 이처럼 | 연산자를 이용하여 타입을 여러 개 연결하는 방식을 유니온 타입 정의 방식이라고 한다

##### Union Type의 장점
