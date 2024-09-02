
```html
<body>
	<div id=“app”>
		//v-bind:프롭스 속성 이름=”상위 컴포넌트의 데이터 이름“
		<app-header v-bind:propsdate=“message”></app-header>
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
