
- 화면의 html 요소들을 DOM을 통해 조작한다
- document.querySelector(‘#app’);
	- 위 코드는 화면에서 아이디가 app인 태그의 내용을 가져온다
```typescript

//화면에서 아이디가 app인 태그를 가져온다
var div = document.querySelector(‘#app’);
//div 태그 안에 good day라고 적는다
div.innerHTML = ’Good Day!’;

```