<template>
	<view class="box">
		<view class="top_box">
			
			<view class="img_box">
				<u-avatar :src="src" size="80"></u-avatar>
				<h3>爱吃大米</h3>
				<text>Lv.9</text>
			</view>
		</view>
		
		<view class="bottom_box">
			<view class="bt" @click="to1">
				<view class="left" >
					<u-icon name="chat" color="#ABABAB" size="28"></u-icon>
					<text>消息通知</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<view class="bt" @click="to2">
				<view class="left">
					<u-icon name="clock" color="#ABABAB" size="24"></u-icon>
					<text> 最近浏览</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<view class="bt" @click="to3">
				<view class="left">
					<u-icon name="edit-pen" color="#ABABAB" size="28"></u-icon>
					<text>草稿</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<view class="bt" @click="to4">
				<view class="left">
					<u-icon name="star" color="#ABABAB" size="28"></u-icon>
					<text>我的收藏</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<view class="bt" @click="to5" >
				<view class="left">
					<u-icon name="share" color="#ABABAB" size="28"></u-icon>
					<text>分享应用</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<view class="bt" @click="to6">
				<view class="left">
					<u-icon name="info-circle" color="#ABABAB" size="24"></u-icon>
					<text>意见反馈</text>
				</view>
				<view class="right">
					<u-icon name="arrow-right" color="#ABABAB" size="28"></u-icon>
				</view>
			</view>
			<u-popup :show="show" mode="bottom"  @close="close">
			        <view class="popup">
			            <view class="top">
			            	<img src="../../static/二维码.png" alt="">
							<text>扫描二维码，立即安装</text>
			            </view>
						<view class="bottom">
							<view class="header">
								<view class="header1">
									<img src="../../static/微信.png" alt="">
									<text>分享微信</text>
									
								</view>
								<view class="header1">
									<img src="../../static/朋友圈.png" alt="">
									<text>分享朋友圈</text>
									
								</view>
								<view class="header1">
									<img src="../../static/复制链接 链接分享.png" alt="">
									<text>分享链接</text>
									
								</view>
								<view class="header1">
									<img src="../../static/相册.png" alt="">
									<text>保存相册</text>
									
								</view>
							</view>
							<view class="btn">
								<u-button text="取消" @click="close"></u-button>
								
							</view>
							
						</view>
			        </view>
				</u-popup>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show:false,
				src: 'https://img0.baidu.com/it/u=1386350086,1849099277&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=500',
				
			}
		},
		methods: {
			to1(){
				uni.navigateTo({
					url:'/pages/infolist/infolist1'
				});
			},
			to2(){
				uni.navigateTo({
					url:'/pages/infolist/infolist2'
				});
			},
			to3(){
				uni.navigateTo({
					url:'/pages/infolist/infolist3'
				});
			},
			to4(){
				uni.navigateTo({
					url:'/pages/infolist/infolist4'
				});
			}
			,to5(){
				
				this.show=true
			},
			to6(){
				uni.navigateTo({
					url:'/pages/infolist/infolist6'
				});
			},
			close() {
			          this.show = false
			          
			        }
		}
	}
</script>

<style scoped>
	.btn{
		margin-top: 15rpx;
	}
	.header{
		margin-top: 20rpx;
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
		
	.header1{
		width: 20%;
		height: 100rpx;
		text-align: center;
	}
	.header1 img{
		width: 60%;
		height: 60%;
		margin: 0 auto;
	}
	.header1 text{
		display: block;
		width: 100%;
		
	}
	.popup{
		width: 100%;
		height: 500rpx;
		
	}
	.popup .top{
		text-align: center;
		display: flex;
		flex-direction: column;
		font-size: 24rpx;
		color: #83A4AD;
	}
	.popup .top img{
		width: 40%;
		height: 250rpx;
		margin: 0 auto;
		margin-top: 10rpx;
	}
	
	.top_box {
		width: 100%;
		height: 400rpx;
		background-color: #95B6BF;
		position: relative;
	}


	.img_box {
		width: 180rpx;
		height: 180rpx;
		text-align: center;
		position: absolute;
		top: 80rpx;
		left: 300rpx;
	}

	.img_box h3 {
		margin-top: 20rpx;
		margin-bottom: 10rpx;
		color: aliceblue;
	}

	.img_box text {
		
		padding: 5rpx;
		background-color: #87B1D7;
	}

	.box_title {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 120rpx;
		background-color: #fff;

	}

	.min_box {
		width: 33%;
		height: 100%;
		text-align: center;
		line-height: 60rpx;
		
		font-weight: 700;

	}
	.min_box h3{
		color:#111C1F ;
	}
	.min_box text{
		color: #83A4AD;
	}
	.bottom_box{
		width: 100%;
		height: 630rpx;
		
	}
	.bt{
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 80rpx;
		background-color: #fff;
		margin-top: 20rpx;
		line-height: 80rpx;
	}
	.bt .left{
		display: flex;
		justify-content: space-between;
		margin-left: 20rpx;
	}
	.box{
		
	}
	.bt .right{
		margin-right: 20rpx;
		margin-top: 15rpx;
	}
</style>
