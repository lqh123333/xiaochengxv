<template>
	<view class="q">
		<view class="book_box" v-for="item in list" :key="item.id" @click="to(item.id)">
			<view class="img_right">
				<img :src="item.img" alt="">
			</view>
			<view class="left">
				<h3>{{item.h3}}</h3>
				<text>{{item.text}}</text>
				<view class="foot">
					
					{{item.time}}
					
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						id:1,
						img:'https://bookcover.yuewen.com/qdbimg/349573/1021617576/150',
						h3:'夜的命名术',
						text:'玄幻奇幻 | 会说话的肘子',
						time:'蓝与紫的霓虹中，浓密的钢铁苍穹下，数据洪流...'
					},
					{
						id:2,
						img:'https://bookcover.yuewen.com/qdbimg/349573/3546912/150',
						h3:'万古神帝',
						text:'玄幻奇幻 | 飞天鱼',
						time:'【NEXTIDEA暨2015星创奖征文大赏(玄幻)】'
					}
					,
					{
						id:3,
						img:'https://bookcover.yuewen.com/qdbimg/349573/1031940621/150',
						h3:'灵境行者',
						text:'科幻灵异 │ 卖报小郎君',
						time:'亘古通今,传闻世有灵境。'
					}
					,
					{
						id:4,
						img:'https://bookcover.yuewen.com/qdbimg/349573/1011058239/150',
						h3:'伏天氏',
						text:'最新:新书《7号基地》发布',
						time:'2022-05-19 15:00:00'
					}
				]
			}
		},
		methods: {
			to(id){
				if(id==1){
					uni.navigateTo({
						url:'/pages/caselist/caselist'
					});
				}else if(id==2){
					uni.navigateTo({
						url:'/pages/caselist/caselist2'
					});
				}else if(id==3){
					uni.navigateTo({
						url:'/pages/caselist/caselist4'
					});
				}else if(id==4){
					uni.navigateTo({
						url:'/pages/caselist/caselist3'
					});
				}
			}
		}
	}
</script>

<style scoped>
	.book_box{
		width: 95%;
		height: 400rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		margin-top: 20rpx;
		padding-bottom: 20rpx;
		border-bottom: 2rpx solid #ccc;
	}
	.img_right{
		width: 35%;
		height: 100%;
	}
	.img_right img{
		margin-top: 15%;
		width: 100%;
		height: 80%;
	}
		
	.left{
		width: 60%;
		height: 100%;
	}
	.left h3{
		font-size: 36rpx;
		font-weight: 900;
		margin: 80rpx 0 60rpx 20rpx;
	}
	.left text{
		display: block;
		width: 100%;
		margin-left: 20rpx;
	}
	.foot{
		
		display: flex;
		flex-direction: row;
		margin: 60rpx 0 20rpx 20rpx;
		font-size: 28rpx;
		color: #B3B3B3;
	}
</style>