<template>
	<view class="q">
		<view class="head">
			<u--textarea v-model="value1" placeholder="请描述您所遇到的问题" height="100"></u--textarea>
		</view>
		<view class="sc">
			<view class="name">
				<u-icon name="account" color="black" size="24"></u-icon>
				<text>姓名:</text>
				<input
				    placeholder="请输入您的姓名"
				    v-model="value2"
				  ></input>
				
			</view>
			<view class="dz">
				<u-icon name="map" color="black" size="24"></u-icon>
				<text>地址:</text>
				<input
				    placeholder="请输入您的地址"
				    v-model="value3"
				  ></input>
				
			</view>
			<view class="dz">
				<u-icon name="phone" color="black" size="24"></u-icon>
				<text>手机号:</text>
				<input
				    placeholder="请输入您的手机号"
				    v-model="value4"
				  ></input>
			</view>
			<view class="bt">
				<u-button type="primary" text="提交"  @click='showToast'></u-button>
				<u-toast ref="uToast" />
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				
				value1: '',
				value2: '',
				value3: '',
				value4: ''
			}
		},
		methods: {
			 showToast() {
			                this.$refs.uToast.show({
			                    title: '登录成功',
			                    type: 'success',
								message:'问题反馈成功',
			                    url: '/pages/infolist/infolist6'
			                })
							this.value1=""
							this.value2=""
							this.value3=""
							this.value4=""
			            }


		}
	}
</script>

<style scoped>
	.head {
		width: 95%;
		margin: 0 auto;
		margin-top: 80rpx;
	}
	.sc {
		width: 95%;
		margin: 0 auto;
		margin-top: 80rpx;
	}
	.name{
		width: 100%;
		height: 60rpx;
		display: flex;
		flex-direction: row;
		padding-bottom: 30rpx;
		border-bottom: 1px solid #ccc;
	}
	.dz{
		width: 100%;
		height: 60rpx;
		display: flex;
		flex-direction: row;
		padding-bottom: 30rpx;
		border-bottom: 1px solid #ccc;
		margin-top: 40rpx;
	}
	text{
		font-size: 40rpx;
	}
	input{
		height: 60rpx;
		margin-left: 20rpx;
	}
	.bt{
		margin-top: 60rpx;
	}
</style>
