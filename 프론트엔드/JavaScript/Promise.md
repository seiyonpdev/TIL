- 콜백 헬을 해결할 수 있는 객체이다
- 함수 실행 성공시 수행하는 함수 resolve와 실패 시 수행하는 함수 reject를 받는 함수 
	executor를 선언하고 Promise객체를 생성하면서 인자로 executor를 준다.
	그리고 Promise객체를 받은 변수를 return한다.

- 위 함수를 실행하면 Promise 객체를 반환받게 되는데 이를 변수에 받아 다음과 같이 처리한다
	- (변수명).then(성공시 콜백함수).catch(실패시 콜백함수)

- 위의 예시에서 then을 계속 체이닝하면 콜백 헬보다 나은 구조로 연쇄적인 작업을 수행할 수 있다.

##### 프로미스의 3가지 상태
1. Pending : 대기. 비동기 처리 로직이 아직 완료되지 않은 상태
2. Fulfilled : 이행. (=완료) 비동기 처리가 완료되어 프로미스가 결과 값을 반환해준 상태
3. Rejected : 실패. 비동기 처리가 실패하거나 오류가 발생한 상태

```typescript
//먼저 new Promise 메서드를 호출하면 대기 상태가 된다
new Promise();

//new Promise 메서드를 호출할 때 콜백 함수를 선언할 수 있고, 콜백 함수의 인자는 resolve, reject이다
new Promise(function(resolve, reject) {
	//..
});

//여기서 콜백 함수의 인자 resolve를 아래와 같이 실행하면 이행 상태가 된다
new Promise(function(resolve, reject){
	resolve();
});

//그리고 이행 상태가 되면 아래와 같이 then()을 이용하여 처리 결과 값을 받을 수 있다

function getData(){
	return new Promise(function(resolve, reject) {
		var data = 100;
		resolve(data);
	});
}

getData().then(function(resolvedData) {
	console.log(resolvedData); //100
});

//실패 상태가 되면 실패한 이유(실패 처리의 결과값)를 catch()로 받을 수 있다
function get

```