#### async
- 함수 선언시 function 키워드 앞에 async 키워드를 써주면 함수가 [[Promise]] 객체를 반환하게 된다
- 따라서 함수의 결과에 바로 then을 사용할 수 있다
#### await
- async 키워드가 붙은 함수 내에서만 사용 가능
- 비동기 함수를 동기적으로 사용할 수 있게 한다. 즉 함수들을 산발적으로 수행하지 않고 순서대로 수행하도록 강제한다.

```ts
//기본 형식
async function 함수명() {
	await 비동기 처리 메서드명();
}

//예시
function fetchItems() {
	return new Promise(function(resolve, reject) {
		var items = [1, 2, 3];
		resolve(items)
	});
}

async function logItems() {
	var resultItems = await fetchItems();
	console.log(resultItems);   //[1,2,3]
}

//예외 처리
async function logTodoTitle() {
	try {
		var user = await fetchUser();
		if (user.id === 1) {
			var todo = await fetchTodo();
			console.log(todo.title);
		}
	} catch (error) {
		console.log(error);
	}
}


```