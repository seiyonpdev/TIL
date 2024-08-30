
```html
<body>
	<div id=“app”>
		<app-header ></app-header>
	</div>
<body/>

<script>
	var appHeader = {
		template: ‘<h1>header</h1>’,
		props: [‘propsdata’]
	}

	new Vue({
		el: ‘#app’,
		components: {
			‘app-header’: appHeader
		},
		data: {
			//Root 컴포넌트의 데이터가 된다
			//이 data를 app-header에 props로 내린다
			message: ‘hi’
		}
	})
</script>
```

- props를 내려보내는 방법
	- <컴포넌트 v-bind: 프롭스 속성 이름=“상위 컴포넌트의 데이터 이름”></컴포넌트>
	- <app-header v-bind: =“message”></app-header>