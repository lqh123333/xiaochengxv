<template>
	<view>
		<view class="box">
			<u-search placeholder="请输入搜索内容" height="90rpx" :showAction=false @focus="focus"></u-search>
			
		</view>
		<view class="switch_box">
			<view class="box_title">
				<view class="min_box" :class="{'active':acId==item.id}" @click="Taggle(item.id)" v-for="item in listT"
					:key="item.id">
					{{item.name}}
				</view>
			</view>
			<view class="box_foot" v-for="item in lists" :key="item.id" v-show="acId==1" @click="to(item.name2)">
				<h2>{{item.name}}</h2>
				
				<img :src="item.img1" alt="" class="img1">
				<img :src="item.img2" alt="">
				<h4>{{item.name2}}</h4>

			</view>
			<view class="box_foot bton" v-show="acId==2" v-for="item in listl" :key="item.id" @click="to">
				<h2>{{item.name}}</h2>
				<img src="../../static/icfont/下箭头.png" alt="" class="img1">
				<view class="le_box">
					<view class="le" v-for="items in item.list2" :key="items.id">
						<img :src="items.img" alt="" class="imger">
						<h4>{{items.name1}}</h4>
					</view>


				</view>

			</view>

		</view>



	</view>
</template>

<script>
	export default {
		data() {
			return {
				listT: [{
					id: 1,
					name: '男生'
				}, {
					id: 2,
					name: '女生'
				}, ],
				acId: 1,
				listl: [{
					id: 1,
					name: '古代言情',
					list2: [{
							id: 1,
							img: '	https://bookcover.yuewen.com/qdbimg/349573/1028412235/150',
							name1: '楚后'
						},
						{
							id: 2,
							img: 'https://bookcover.yuewen.com/qdbimg/349573/1030220536/150',
							name1: '玉无香'
						},
						{
							id: 3,
							img: '	https://bookcover.yuewen.com/qdbimg/349573/1032539444/150',
							name1: '踏枝'
						}, {
							id: 4,
							img: '	https://bookcover.yuewen.com/qdbimg/349573/1033406792/150',
							name1: '又逢君'
						}
					]
				}, {
					id: 2,
					name: '现代言情',
					list2: [{
							id: 1,
							img: '	https://bookcover.yuewen.com/qdbimg/349573/1023199770/150',
							name1: '致命偏宠'
						},
						{
							id: 2,
							img: 'https://bookcover.yuewen.com/qdbimg/349573/1033347026/150',
							name1: '诱他上瘾'
						},
						{
							id: 3,
						 img: 'https://bookcover.yuewen.com/qdbimg/349573/1019381476/150',
						 name1: '丁薇记事'
						}
					]
				}, {
					id: 3,
					name: '浪漫青春',
					list2: [{
							id: 1,
							img: 'https://bookcover.yuewen.com/qdbimg/349573/1031402330/150',
						 name1: '佛系小青梅'
						},
						{
							id: 2,
							img: '	https://bookcover.yuewen.com/qdbimg/349573/1027186439/150',
							name1: '他明明心动'
						},
						{
							id: 3,
						 img: 'https://bookcover.yuewen.com/qdbimg/349573/1026610688/150',
							name1: '你甜到犯规了'
						}
						,
						{
							id: 4,
						 img: 'https://bookcover.yuewen.com/qdbimg/349573/1028817914/150',
							name1: '不只是心动'
						}
					]
				}],
				lists: [{
						id: 1,
						name: '玄幻推荐',
						
						img1: '/static/icfont/下箭头.png',
						img2: 'https://bookcover.yuewen.com/qdbimg/349573/1021617576/150',
						name2: '玄幻'
					},
					{
						id: 2,
						name: '历史推荐',
						
						img1: '/static/icfont/下箭头.png',
						img2: 'https://bookcover.yuewen.com/qdbimg/349573/1032822816/300',
						name2: '历史'
					},
					{
						id: 3,
						name: '都市推荐',
						
						img1: '/static/icfont/下箭头.png',
						img2: '	https://bookcover.yuewen.com/qdbimg/349573/1033991798/300',
						name2: '都市'
					},
					{
						id: 4,
						name: '科幻精选',
						
						img1: '/static/icfont/下箭头.png',
						img2: 'https://bookcover.yuewen.com/qdbimg/349573/1639199/300',
						name2: '科幻'
					},
					{
						id: 5,
						name: '奇幻作品',
						
						img1: '/static/icfont/下箭头.png',
						img2: 'https://bookcover.yuewen.com/qdbimg/349573/1017141/300',
						name2: '奇幻'
					},


				]
			}
		},
		methods: {
			Taggle(id) {
				this.acId = id
			},
			to(na){
				
				uni.navigateTo({
					url:'/pages/listlist/list1?n='+na
				});
			},
				
			focus(){
				uni.navigateTo({
					url:'/pages/search/search'
				});
			}
		}
	}
</script>

<style scoped>
	.box {

		width: 100%;
		height: 200rpx;
		background-color: #95B6BF;
		border-bottom-left-radius: 30%;
		border-bottom-right-radius: 30%;
		padding: 10px;
		box-sizing: border-box;
	}


	.switch_box {
		width: 94%;
		height: 520rpx;
		margin: 0 auto;
		margin-top: -40rpx;
	}

	.box_title {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 100rpx;
		background-color: aquamarine;
	}

	.min_box {
		width: 50%;
		height: 100%;
		background-color: #84A4AB;
		text-align: center;
		line-height: 110rpx;
		font-weight: 700;

	}

	.active {
		background-color: #d6e0d6;
	}

	.box_foot {
		width: 100%;
		height: 400rpx;
		text-align: center;
		margin-top: 40rpx;
		margin-bottom: 350rpx;


	}
	.bton{
		margin-bottom: 600rpx;
	}
	.box_foot img {
		width: 350rpx;
		height: 400rpx;
	}

	.box_foot h4,
	h5 {
		color: #303133;
		font-weight: 500;
	}

	.box_foot .img1 {
		width: 40rpx;
		height: 50rpx;
		margin: 0 auto;
		display: block;
	}

	.box_foot h2 {
		color: #303133;
	}

	.le {
		width: 45%;
		height: 400rpx;

	}

	.le h4 {
		font-weight: 200;
	}

	.le img {
		width: 100%;
		height: 300rpx;
	}

	.le_box {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-around;
		flex-wrap: wrap
	}
	
</style>
