<template>
	<view>
		<view>
			<button @click="requset" type="primary">发送请求</button>
		</view>
		<view>
			<button @click="add" type="primary">添加拦截器请求</button>
		</view>
		<view>
			<button @click="remove" type="warn">删除拦截器请求</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {
			requset() {
				console.log("发送请求");
				uni.request({
					url: '/api/test',
					method: 'POST',
					timeout: 500,
					success: (resp) => {
						console.log("requset 成功的回调", resp);
					},
					fail: (resp) => {
						console.log("requset 失败的回调", resp);
					}
				})
			},
			add() {
				console.log("添加拦截器");
				uni.addInterceptor('request', {
					invoke: (e) => {
						console.log('拦截前触发 ', e);
						//return false;
					},
					returnValue: (e) => {
						console.log('方法调用后触发，处理返回值 ', e);
					},
					success: (e) => {
						console.log('成功回调拦截 ', e);
					},
					fail: (e) => {
						console.log('失败回调拦截 ', e);
					},
					complete: (e) => {
						console.log('完成回调拦截 ', e);
					},
				})
			},
			remove() {
				console.log("删除拦截器");
				uni.removeInterceptor('request');
			}
		}
	}
</script>

<style>
	button {
		margin: 10px;
	}
</style>