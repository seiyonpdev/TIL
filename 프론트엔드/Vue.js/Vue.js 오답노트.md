

- html 태그의 속성에 vue 문법을 쓰고 싶을때 속성 앞에 **:(콜론)** 을 붙여야 한다
	- 콜론을 붙이지 않으면 뷰가 코드를 일반 html 문법으로 인식하며 뷰의 기능을 사용할 수 없다
```ts
//앞에 콜론이 없어서 뷰 문법을 사용 못함
<input type=“isPwVisible ? ‘text’ : ‘password’”/>

//콜론이 있어야 뷰 문법 사용 가능
<input :type=“isPwVisible ? ‘text’ : ‘password’”/>
```

- v-on:click을 @click으로 축약할 수 있다
