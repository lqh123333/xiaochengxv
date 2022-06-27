<template>
	<view class="h">
		<view class="list_box">
			
			<view id="demo1" class="scroll-view-item " v-for="item in list4" :key="item.id">
				
				<view class="img_box1">
					<img :src="item.img" alt="">
				</view>
				<view class="img_right1">
					<h4>{{item.h1}}</h4>
					<view class="text3">{{item.text}}</view>
					<view class="bottom">
						<view class="left">
							<u-icon name="account" size="20"></u-icon>
							{{item.user}}
						</view>
						<view class="right">
							{{item.title}}
						</view>
					</view>
				</view>
		
			</view>
		</view>
	
			
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				list4: [{
						id: 1,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1033806888/150',
						h1: '曾经，我想做个好人',
						text: '穿城到—个有着各种奇怪能力，灾难生物,厄运宝具的危险世界。方泽只想...',
						user:'常世',
						title:'连载中 136.56万字'
					},
					{
						id: 2,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1032778366/150',
						h1: '择日飞升',
						text: '作为捕融蛇者，许应一直老老实实勤恳本分,直到这一天，他捉到一条不一...',
						user:'宅猪',
						title:'连载中 59.91万字'
					},
					{
						id: 3,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1021617576/150',
						h1: '夜的命名术',
						text: '蓝与紫的霓虹中，浓密的钢铁苍穹下，数据洪流的前端，是科技革命之后...',
						user:'会说话的肘子',
						title:'连载中 717.78万字'
					},
					{
						id: 4,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1016872810/150',
						h1: '洪主',
						text: '大江东去，洗不尽人族英雄血。自六千年前成阳人帝起兵,这天下，便是我人族天...',
						user:'锋仙',
						title:'连载中 517.12万字'
					},
					{
						id: 5,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1033315243/150',
						h1: '超维武仙',
						text: '大旻无道，神器更易,此乃天命!',
						user:'万事皆虚',
						title:'连载中 40.66万字'
					},
					{
						id: 6,
						img: '	https://bookcover.yuewen.com/qdbimg/349573/1029169548/150',
						h1: '机械炼金术士',
						text: '幽暗的地下城，这里埋藏了数之不尽的古代遗迹和宝藏。诡异，畸变，诅咒...',
						user:'盲侯',
						title:'连载中 209.09万字'
					}
				],
			}
		}
	}
</script>

<style scoped>
	.right{
		width: 50%;
		text-align: end;
		font-size: 24rpx;
		color:#969BA3;
	}
	.bottom{
		margin-top: 20rpx;
		display: flex;
		flex-direction: row;
	}
	.left{
		width: 50%;
		display: flex;
		flex-direction: row;
		font-size: 28rpx;
		color:#969BA3;
	}
	.list_box {
		width: 100%;
		margin-top: 10px;
	
	}
	
	.scroll-view-item {
		display: flex;
		justify-content: space-between;
		height: 350rpx;
	
		text-align: left;
		font-size: 36rpx;
		border-bottom: 1rpx solid #ccc;
		padding: 15rpx;
		box-sizing: border-box;
	
	}
	
	.scroll-view-item .img_right {
		width: 100%;
		height: 100%;
	}
	.scroll-view-item .img_right h3 {
		font-size: 36rpx;
		width: 100rpx;
		height: 20rpx;
	
	}
	.scroll-view-item .img_right .h33{
		width: 130rpx;
	}
	
	.scroll-view-item .img_right .text3 {
		margin-top: 25rpx;
		width: 100%;
		height: 200rpx;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		flex-wrap: wrap;
	
	}
	.img_box1 {
		width: 35%;
		height: 300rpx;
		margin-top: 10rpx;
	}
	.img_box1 img{
		width: 100%;
		height: 300rpx;
	}
	.img_right1{
		width: 60%;
		margin-top: 30rpx;
		
	} 
	h2,h3{
		font-size: 56rpx;
		font-weight: 900;
	}
	h4{
		font-size: 36rpx;
		font-weight: 900;
	}
</style>