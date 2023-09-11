<template>
	<input class="input text"
           :value="modelValue"
           :placeholder="placeholder"
           @input="$emit('update:modelValue', $event.target.value)">
</template>

<script>
export default {
	name: "CustomInput",
	props: {
		placeholder: {
			type: String,
			required: false
		},
		modelValue: {
			type: String,
			required: true
		},
	},
}
</script>

<style lang="scss" scoped>
@import "@/components/UI/CustomInput/style.scss";
</style>
