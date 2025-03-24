
#### commonPanel
```vue
<template>
	<section>
		<h3 @click=“isOpen !isOpen”>
			{{ title }}
			<button class=“btn_fold” :class=“{ close: !isOpen }”>
				접기
			</button>
		</h3>
		<div class=“details” :class=“{ close: !isOpen }”>
			<slot name=“body” />
		</div>
	</section>
</template>
<script setup>
import { ref } from ‘vue’

const { title } = defineProps({
	title: {
		type: String,
		default: ‘’
	}
})

const isOpen = ref(true)

</script>
```

#### commonDatePicker
```vue
<template>
	<DatePicker v-model=“date” :input-debounce=“500” :max-date :min-date :popover>
		<template #header-title=“pages”>
		{{ pages.title.split(‘ ’)[1] }}년 {{ pages.title.split(‘ ‘) }}
		</template>
		<template #default=“{ inputValue, inputEvents }”>
			<input 
				type=“text”
				class=“datepicker”
				:value=“inputValue”
				:disabled=“disabled”
				v-on=“inputEvents”
			/>
		</template>
	</DatePicker>
</template>
<script setup lang=“ts”>
import ‘v-calendar/style.css’
import { DatePicker } from ‘v-calendar’
import { ref } from ‘vue’
import { PopoverOptions } from ‘v-calendar/dist/types/src/utils/popovers.js’

const { minDate, search } = defineProps({
	minDate: {
		type: Date,
		default: null
	},
	maxDate: {
		type: Date,
		default: null
	},
	search: {
		type: Boolean,
		default: false
	},
	disabled: {
		type: Boolean,
		default: false
	}
})

const popover = ref<Partial<PopoverOptions>>({
	visibility: ‘click’
})

const date = ref(search ? ‘’ : new Date())


defineExpose({
	date
})

</script>
```