<template>
	<view>
		{{base64}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				base64: '',
			}
		},
		methods: {

		},
		onShow() {
			const arrayBuffer = new Uint8Array([55, 55, 55])
			this.base64 = uni.arrayBufferToBase64(arrayBuffer)
			console.log(this.base64);
		}
	}
</script>

<style>

</style>