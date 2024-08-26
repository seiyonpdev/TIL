- 타입 추론 : 타입스크립트가 코드를 해석해 나가는 동작을 의미한다

```typescript
//타입 추론의 기본
//아래 x는 타입을 지정하지 않아도 number로 간주한다
let x = 3;

//가장 적절한 타입(Best Common Type)
//타입은 보통 몇 개의 표현식을 바탕으로 추론한다. 그리고 그 표현식을 이용하여 가장 근접한 타입을 추론하는데 이 가장 근접한 타입을 Best Common Type이라고 한다
let arr = [0, 1, null];

//문맥상의 타이핑(Contextual Typing)
//타입스크립트는 문맥상으로도 타입을 결정할 수 있다
window.onmousedown = function(mouseEvent) {
	console.log(mouseEvent.button);   //OK
	console.log(mouseEvent.kangaroo); //Error
}
//위 코드를 타입스크립트 검사기 관점에서 보면 window.onmousedown에 할당되는 함수의 타입을 추론하기 위해 window.onmousedown 타입을 검사한다
//타입 검사가 끝나고 나면 함수의 타입이 마우스 이벤트와 연관이 있다고 추론하기 때문에 mouseEvent인자에 button속성은 있지만 kangaroo속성은 없다는 결론을 내린다

window.onscroll = function(uiEvent) {
	console.log(uiEvent.button);  //Error
}
const handler = function(uiEvent) {
	console.log(uiEvent.button); //OK
}
//위 경우에 window.onscroll은 uiEvent를 받는다고 추론했기 때문에 button속성이 없다고 추론한다. 반면 handler는 그냥 변수이기 때문에 변수만으로는 타입을 추정하기 어려워 아무 에러가 나지 않는다

```