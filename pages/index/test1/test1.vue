<template>
	<view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				test:'123456789',
			}
		},
		methods: {
			
		},
		onShow() {
			const arrayBuffer=uni.base64ToArrayBuffer(this.test);
			console.log(arrayBuffer);
		}
	}
</script>

<style>

</style>
