
```html
<body>
	<div id=“app”>
		//v-on: 하위 컴포넌트에서 발생한 이벤트명=“상위 컴포넌트의 메서드명”
		<app-header v-on: pass=“logText”></app-header>
	</div>
	<script>
		var appHeader = {
			template: 
				‘<button v-on:click=“passEvent”>
				Click
				</button>’
			methods: {
				passEvent: function() {
					this.$emit(‘pass’);
				}
			}
		}
		new Vue({
			el: ‘#app’
			components: {
				‘app-header’: appHeader
			}
			methods: {
				logText: function() {
					console.log(‘hi’);
				}
			}
		})
	</script>
</body>

```