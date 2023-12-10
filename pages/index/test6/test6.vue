<template>
	<view>

	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		},
		onShow() {
            console.log(uni.canIUse('getSystemInfoSync.return.screenWidth'));
            console.log(uni.canIUse('getSystemInfo.success.screenWidth'));
            console.log(uni.canIUse('showToast.object.image'));
            console.log(uni.canIUse('request.object.method.GET'));
            console.log(uni.canIUse('live-player'));
            console.log(uni.canIUse('text.selectable'));
            console.log(uni.canIUse('button.open-type.contact'));
			console.log(uni.canIUse('request'));
		}
	}
</script>

<style>

</style>
