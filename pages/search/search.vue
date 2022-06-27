<template>
	<view class="q">
		<view class="search">
			<u-search placeholder="请输入搜索内容" v-model="kw" :showAction="false" @change='change' @search='search'>
			</u-search>
		</view>
		<view class="allbox" v-show="show1">
			<view class="search_box">
				<view class="head">
					<view class="left">
						<h3>热门搜索</h3>
					</view>
					<view class="right" @click="show">
						<u-icon name="reload" size="20"></u-icon>换一批
					</view>
				</view>
				<view class="body" v-if="show2">
					<view class="bleft">
						<p v-for="item in listleft2" :key="item.id" @click="Form(item.title)"><text
								:class="item.c">{{item.id}}</text> {{item.title}}</p>


					</view>
					<view class="bright">
						<p v-for="item in listright2" :key="item.id" @click="Form(item.title)"><text
								:class="item.c">{{item.id}}</text> {{item.title}}</p>

					</view>

				</view>
				<view class="body" v-if="!show2">
					<view class="bleft">
						<p v-for="item in listleft" :key="item.id" @click="Form(item.title)"><text
								:class="item.c">{{item.id}}</text> {{item.title}}</p>


					</view>
					<view class="bright">
						<p v-for="item in listright" :key="item.id" @click="Form(item.title)"><text
								:class="item.c">{{item.id}}</text> {{item.title}}</p>

					</view>

				</view>
			</view>
			<view class="search_box1">
				<view class="head">
					<view class="left">
						<h3>搜索历史</h3>
					</view>
					<view class="right" @click="clear">
						清空历史
					</view>
				</view>
				<view class="ls">
					<text class="lsbox" v-for="(item,index) in list" :key="index" @click="Form(item)">{{item}}</text>


				</view>

			</view>

		</view>
		<view class="search_b" v-show="!show1">
			<view class="b_box" v-for="(item,index) in a" :key="index">
				{{item}}
			</view>
		</view>
	</view>


</template>

<script>
	export default {
		data() {
			return {
				a:[],
				kw: '',
				arr: [],
				show2: false,
				show1: true,
				list: ['万古神帝', '伏天氏'],
				listleft: [{
						id: 1,
						c: 't1',
						title: '深空彼岸'
					},
					{
						id: 3,
						c: 't1',
						title: '恐怖复苏'
					},
					{
						id: 5,
						title: '沧元图'
					},
					{
						id: 7,
						title: '斗破苍穹'
					},
					{
						id: 9,
						title: '宇宙职业选手'
					}
				],
				listright: [{
						id: 2,
						c: 't1',
						title: '吞噬星空'
					},
					{
						id: 4,
						title: '公子别秀'
					},
					{
						id: 6,
						title: '人族镇守使'
					},
					{
						id: 8,
						title: '无敌神主'
					},
					{
						id: 10,
						title: '牧神记'
					}
				],
				listleft2: [{
						id: 1,
						c: 't1',
						title: '我有一剑'
					},
					{
						id: 3,
						c: 't1',
						title: '夜的命名术'
					},
					{
						id: 5,
						title: '斗罗大陆'
					},
					{
						id: 7,
						title: '万相之王'
					},
					{
						id: 9,
						title: '大魏芳华'
					}
				],
				listright2: [{
						id: 2,
						c: 't1',
						title: '7号基地'
					},
					{
						id: 4,
						title: '万古神帝'
					},
					{
						id: 6,
						title: '星门'
					},
					{
						id: 8,
						title: '不科学御兽'
					},
					{
						id: 10,
						title: '伏天氏'
					}
				]
			}
		},
		methods: {
			Form(i) {
				this.kw = i
				
				if (this.list.indexOf(i)== -1) {
					this.list.push(this.kw)
				}
			},
			search() {
				this.list.push(this.kw)
			},
			show() {
				this.show2 = !this.show2
			},
			clear() {
				this.list = []
			},
			change() {
				
				if (this.kw == '') {
					this.show1 = true
				} else {
					this.show1 = false
				}
				uni.request({
					url:"http://suggestion.baidu.com/su?cb=callback&wd="+this.kw,
					method:'GET',
					success:(res)=> {
						let str=res.data.slice(9,-2)
						let arr=str.split(",").slice(3,-2)
					  this.a=arr
					  console.log(this.a);
					}
				
				})
				
			}
		}
	}
</script>

<style scoped>
	.b_box{
		width: 90%;
		margin: 0 auto;
		margin-top: 50rpx;
		
	}
	.lsbox {
		display: inline-block;
		padding: 15rpx;
		background-color: #F1F1F1;
		border-radius: 15%;
		margin-top: 20rpx;
		margin-right: 20rpx;
	}

	.ls {
		width: 90%;
		height: 400rpx;
		margin: 0 auto;
		margin-top: 30rpx;

	}

	.t1 {
		color: orange;
	}

	text {
		margin-right: 15rpx;
		font-weight: 600;
	}

	p {
		margin: 30rpx 0 0 10rpx;
	}

	.bleft,
	.bright {
		width: 50%;
	}

	.body {
		width: 90%;
		margin: 0 auto;
		height: 400rpx;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	.search {
		width: 90%;
		margin: 0 auto;
		margin-top: 30rpx;
	}

	.search_box {
		width: 90%;
		margin: 0 auto;
	}

	.search_box1 {
		width: 90%;
		margin: 0 auto;
		margin-top: 50rpx;
	}

	.head {
		margin: 30rpx 0 0 40rpx;
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	.left {
		width: 70%;
	}

	.right {
		width: 30%;
		display: flex;
		flex-direction: row;


	}
</style>
