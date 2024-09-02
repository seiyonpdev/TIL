
```html
<body>
	<div id=“app”>
		<app-header></app-header>
	</div>
	<script>
		var appHeader = {
			template: 
				‘<button v-on:click=“passEvent”>
				Click
				</button>’
			methods: {
				passEvent: function() {
					this.$emit
				}
			}
		}
		new Vue({
			el: ‘#app’
			components: {
				‘app-header’: appHeader
			}
		})
	</script>
</body>

```