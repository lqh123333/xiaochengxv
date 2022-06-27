<template>
	<view class="box" >
		<view class="book_box" v-for="item in list" :key="item.id" @click="to(item.id)">
			<view class="img_right">
				<img :src="item.img" alt="">
			</view>
			<view class="left">
				<h3>{{item.h3}}</h3>
				<text>{{item.text}}</text>
				<view class="foot">
					<u-icon name="clock" color="#B3B3B3" size="20"></u-icon>
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
						text:'最新：831、师姑，王小九',
						time:'2022-06-17 00:00:00'
					},
					{
						id:2,
						img:'https://bookcover.yuewen.com/qdbimg/349573/3546912/150',
						h3:'万古神帝',
						text:'最新:第三千七百六十六章 青鹿',
						time:'2022-06-16 02:00:00'
					}
					,
					{
						id:3,
						img:'https://bookcover.yuewen.com/qdbimg/349573/1011058239/150',
						h3:'伏天氏',
						text:'最新:新书《7号基地》发布',
						time:'2022-05-19 15:00:00'
					},
					{
						id:4,
						img:'https://bookcover.yuewen.com/qdbimg/349573/1031940621/150',
						h3:'灵境行者',
						text:'最新:第一百七十一章 危机来临',
						time:'2022-05-06 18:51:00'
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
						url:'/pages/caselist/caselist3'
					});
				}else if(id==4){
					uni.navigateTo({
						url:'/pages/caselist/caselist4'
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
