<template>
	<view class="content">

		<view class="box">
			<u-search placeholder="请输入搜索内容" height="90rpx" :showAction=false @focus='focus'></u-search>
		</view>
		<view class="swiper_box">
			<u-swiper :list="list1" height="170" :indicator=true :circular=true></u-swiper>
		</view>
		
		<view class="switch_box">
			<view class="box_title">
				<view class="min_box" :class="{'active':acId==item.id}" @click="Taggle(item.id)" v-for="item in listT"
					:key="item.id">
					{{item.name}}
				</view>
			</view>
			<view class="box_foot">
				<scroll-view :scroll-top="scrollTop" scroll-y="true" show-scrollbar=true v-show="acId==1">
					<view id="demo1" class="scroll-view-item1 ">
						<view class="img_box">
							<view class="text"
								style="color: #A11313;font-weight: 700;margin-top: 30rpx;margin-bottom: 20rpx;padding-left: 20rpx;">
								边城少年，扬刀猎冠:日月风华

							</view>
							<view class="textt" v-for="item in textt" :key="item.id" >
								{{item.name}}
							</view>
						</view>


					</view>


				</scroll-view>
				<scroll-view :scroll-top="scrollTop" scroll-y="true" show-scrollbar=true v-show="acId==2">
					<view id="demo1" class="scroll-view-item " v-for="item in list2" :key="item.id">

						<view class="img_right">
							<view class="header">
								<view class="lefter">
									<h3>{{item.h3}}</h3><text>共{{item.num}}本作品</text>
								</view>
								<view class="righter">
									<u-icon name="arrow-right" color="#ccc" size="28"></u-icon>
								</view>
							</view>
							<view class="text3">
								<view class="tag" v-for="items in item.title" :key="items.id">{{items.t}}</view>
							</view>
						</view>
					</view>
				</scroll-view>
				<scroll-view :scroll-top="scrollTop" scroll-y="true" show-scrollbar=true v-show="acId==3">
					<view id="demo1" class="scroll-view-item " v-for="item in list3" :key="item.id">
						<view class="img_right">
							<view class="header">
								<view class="lefter">
									<h3 class='h33'>{{item.h}}</h3>
								</view>
								<view class="righter">
									
									<u-icon name="arrow-right" color="#ccc" size="28"></u-icon>
								</view>
							</view>
							<view class="text4" v-for="items in item.title" :key="items.id">
								<view class="t_left">
									{{items.name}}
								</view>
								<view class="t_right">
									{{items.num}}
								</view>
							</view>
						</view>

					</view>


				</scroll-view>
			</view>
		</view>

		<view class="list_box">
			<view class="title" @click="to1">
				<view class="ti_left">
					<h2>畅销精选</h2>
				</view>
				<view class="ti_right">
					<text>更多</text>
					<u-icon name="arrow-right" color="#ccc" size="28"></u-icon>
				</view>
			</view>
			<view id="demo1" class="scroll-view-item " v-for="item in list4" :key="item.id">
				
				<view class="img_box1">
					<img :src="item.img" alt="">
				</view>
				<view class="img_right1">
					<h4>{{item.h1}}</h4>
					<view class="text3">{{item.text}}</view>
				</view>

			</view>
		</view>
		<view class="list_box">
			<view class="title" @click="to2">
				<view class="ti_left">
					<h2>猜你喜欢</h2>
				</view>
				<view class="ti_right">
					<text>更多</text>
					<u-icon name="arrow-right" color="#ccc" size="28"></u-icon>
				</view>
			</view>
			<view id="demo1" class="scroll-view-item " v-for="item in list5" :key="item.id">
				
				<view class="img_box1">
					<img :src="item.img" alt="">
				</view>
				<view class="img_right1">
					<h4>{{item.h1}}</h4>
					<view class="text3">{{item.text}}</view>
				</view>
		
			</view>
		</view>
		<view class="list_box">
			<view class="title" @click="to3">
				<view class="ti_left">
					<h2>新书抢鲜</h2>
				</view>
				<view class="ti_right">
					<text>更多</text>
					<u-icon name="arrow-right" color="#ccc" size="28"></u-icon>
				</view>
			</view>
			<view id="demo1" class="scroll-view-item " v-for="item in list6" :key="item.id">
				
				<view class="img_box1">
					<img :src="item.img" alt="">
				</view>
				<view class="img_right1">
					<h4>{{item.h1}}</h4>
					<view class="text3">{{item.text}}</view>
				</view>
		
			</view>
		</view>
	</view>


</template>

<script>
	export default {
		data() {
			return {
				textt: [{
						id: 1,
						name: '[都市]这软饭我吃定了:身怀绝技叱诧风云'

					}, {
						id: 2,
						name: '[科幻]星际生存从侵略开始:征服星辰大海'

					},
					{
						id: 3,
						name: '[历史]重生成了大明朱允炆:开万世之太平'

					},
					{
						id: 4,
						name: '[都市]老实人逆袭2003:支棱起来战今生。'

					},
					{
						id: 5,
						name: '[仙侠]我绑定了搞事修仙系统:奖励真香!'

					},
					{
						id: 6,
						name: '[武侠]酒剑四方:吾辈皆当悬文胆，清己心'

					}
				],
			
				scrollTop: 0,
				acId: 1,
				list1: [
					'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/1f6c4b6e8cba9e19bf3d8471cc51a924.jpg',
					'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/a6b0ade481e92b6cdf57366f2e259ce0.jpg',
					'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/4e4807969333dc0cffc914f5598644c4.jpg',
					'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/8999891c8e3a9eb9e20a6814370814cb.jpg'
				],
				listT: [{
					id: 1,
					name: '新书推荐'
				}, {
					id: 2,
					name: '作品分类'
				}, {
					id: 3,
					name: '排行榜'
				}],
				list2: [{
						id: 1,
						h3: '玄幻',
						num: 721722,
						title: [{
								id: 1,
								t: '东方玄幻'
							},
							{
								id: 2,
								t: '异世大陆'
							}, {
								id: 3,
								t: '王朝争霸'
							}, {
								id: 4,
								t: '高武世界'
							}
						]
					},
					{
						id: 2,
						h3: '奇幻',
						num: 661722,
						title: [{
								id: 1,
								t: '现代魔法'
							},
							{
								id: 2,
								t: '剑与魔法'
							}, {
								id: 3,
								t: '史诗奇幻'
							}, {
								id: 4,
								t: '神秘幻想'
							}, {
								id: 5,
								t: '历史神话'
							}
						]
					},
					{
						id: 3,
						h3: '武侠',
						num: 421722,
						title: [{
								id: 1,
								t: '传统武侠'
							},
							{
								id: 2,
								t: '武侠幻想'
							}, {
								id: 3,
								t: '国术无双'
							}, {
								id: 4,
								t: '古武未来'
							}, {
								id: 5,
								t: '武侠同人'
							}
						]
					},
					{
						id: 4,
						h3: '都市',
						num: 374244,
						title: [{
								id: 1,
								t: '爱情婚姻'
							},
							{
								id: 2,
								t: '都市生活'
							}, {
								id: 3,
								t: '都市异能'
							}, {
								id: 4,
								t: '青春校园'
							}, {
								id: 5,
								t: '商战职场'
							}, {
								id: 6,
								t: '娱乐明星'
							}
						]
					},
					{
						id: 5,
						h3: '历史',
						num: 771722,
						title: [{
								id: 1,
								t: '秦汉三国'
							},
							{
								id: 2,
								t: '五代十国'
							}, {
								id: 3,
								t: '两宋元明'
							}, {
								id: 4,
								t: '清史民国'
							}, {
								id: 5,
								t: '外国历史'
							}
						]
					}
				],
				list3:[
					{
						id:1,
						h:'月票榜',
						title:[
							{
								id:1,
								name:'我有一剑',
								num:6754436
							},
							{
								id:2,
								name:'星海王座',
								num:5554436
							},
							{
								id:3,
								name:'盖世人王',
								num:4354436
							}
						]
					},
					{
						id:2,
						h:'畅销榜',
						title:[
							{
								id:1,
								name:'夜的命名术',
								num:6454436
							}
							,
							{
								id:2,
								name:'星海王座',
								num:6254436
							},
							{
								id:3,
								name:'深空彼岸',
								num:5754436
							}
						]
					},
					{
						id:3,
						h:'阅读榜',
						title:[
							{
								id:1,
								name:'夜的命名术',
								num:6554436
							}
							,
							{
								id:2,
								name:'万古神帝',
								num:6354436
							},
							{
								id:3,
								name:'剑来',
								num:5854436
							}
						]
					}
					
				],
				list4: [{
						id: 1,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1033806888/150',
						h1: '曾经，我想做个好人',
						text: '穿城到—个有着各种奇怪能力，灾难生物,厄运宝具的危险世界。方泽只想...'
					},
					{
						id: 2,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1032778366/150',
						h1: '择日飞升',
						text: '作为捕融蛇者，许应一直老老实实勤恳本分,直到这一天，他捉到一条不一样...'
					},
					{
						id: 3,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1021617576/150',
						h1: '夜的命名术',
						text: '蓝与紫的霓虹中，浓密的钢铁苍穹下，数据洪流的前端，是科技革命之后...'
					}
				],
				list5: [{
						id: 1,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1014017925/150',
						h1: '夫人你马甲又掉了',
						text: '本文出版名《一万次心动》，新书《大神你人设崩了》~【本文专注扒马...'
					},
					{
						id: 2,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/3678827/150',
						h1: '君九龄',
						text: '太康三年冬，阳城北留镇宁家来了—个上门认亲的女孩子...'
					},
					{
						id: 3,
						img: '	https://bookcover.yuewen.com/qdbimg/349573/2586940/150',
						h1: '仙灵图谱',
						text: '万年前的倾天之祸，沧溟界与各界隔绝，通天大道就此断绝...'
					}
				],
				list6: [{
						id: 1,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1033052560/150',
						h1: '天庭最后一个大佬',
						text: '简介:三百年前的天界，斗战胜佛踏平了雷音寺，二郎真君劈开了凌霄殿...'
					},
					{
						id: 2,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1033544120/150',
						h1: '大夏文圣',
						text: '神洲。大夏王朝。永盛十二年。顾锦年穿越而来，惊奇发现这是个仙武并存...'
					},
					{
						id: 3,
						img: 'https://bookcover.yuewen.com/qdbimg/349573/1031940621/150',
						h1: '灵境行者',
						text: '亘古通今，传闻世有灵境。关于灵境的说法，历朝历代的名人雅士众说纷纭...'
					}
				]
			}
		},
		
		methods: {
			Taggle(id) {
				this.acId = id
			},
			to1() {
				uni.navigateTo({
					url:'/pages/indexlist/indexlist'
				});
			},
			to2() {
				uni.navigateTo({
					url:'/pages/indexlist/indexlist2'
				});
			}
			,
			to3() {
				uni.navigateTo({
					url:'/pages/indexlist/indexlist3'
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
		height: 350rpx;
		background-color: #95B6BF;
		border-bottom-left-radius: 30%;
		border-bottom-right-radius: 30%;
		padding: 10px;
		box-sizing: border-box;
	}

	.swiper_box {

		width: 94%;
		height: 300rpx;
		margin: 0 auto;
		margin-top: -200rpx;
		border-top-left-radius: 5%;
		border-top-right-radius: 5%;
		border-bottom-left-radius: 10%;
		border-bottom-right-radius: 10%;
		box-shadow: 0 0 6px #000;
		overflow: hidden;
	}

	

	.switch_box {
		width: 94%;
		height: 520rpx;
		margin: 0 auto;
		margin-top: 30rpx;
	}

	.box_title {
		display: flex;
		justify-content: space-between;
		width: 100%;
		height: 100rpx;
		background-color: aquamarine;
	}

	.min_box {
		width: 33%;
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

	}

	scroll-view {
		height: 100%;
	}

	.scroll-view-item {
		display: flex;
		justify-content: space-between;
		height: 250rpx;

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

	.scroll-view-item .img_right .header {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}

	.scroll-view-item .img_right .header .lefter {
		width: 70%;
		display: flex;
		flex-direction: row;

	}

	.scroll-view-item .img_right .header .lefter text {
		font-size: 30rpx;
		margin-top: 5rpx;
	}

	.scroll-view-item .img_right .header .righter {
		width: 30%;
		margin-left: 200rpx;
		height: 30rpx;
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
	.scroll-view-item .img_right .text4{
		
		width: 100%;
		height: 60rpx;
		line-height: 100rpx;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		flex-wrap: wrap;
	}
	.scroll-view-item .img_right .text4 .t_left{
		
		width: 45%;
	}
	
	.scroll-view-item .img_right .text4 .t_right{
		
		text-align: end;
		width: 45%;
		color: #ccc;
	}

	.scroll-view-item .img_right .text3 .tag {
		padding: 5rpx;
		margin-left: 10rpx;
		text-align: center;
		line-height: 50rpx;
		width: 200rpx;
		height: 50rpx;
		border: 2rpx solid #84A4AB;
		border-radius: 25rpx;
	}

	.scroll-view-item1 {
		display: flex;
		flex-direction: column;
		height: 400rpx;
		text-align: initial;
		font-size: 36rpx;

		padding: 10rpx;
		box-sizing: border-box;
	}

	.scroll-view-item1 .img_box {
		width: 100%;
		height: 100%;

	}

	.scroll-view-item1 .img_box .textt {
		width: 100%;
		height: 60rpx;
		padding: 10rpx;
	}
	


	.img_box {
		width: 35%;
		height: 100%;

	}

	img {
		margin-left: 5%;
		width: 90%;
		height: 100%;
	}


	.list_box {
		width: 100%;
		margin-top: 20px;

	}
	.list_box .title{
		margin: 0 auto;
		width: 96%;
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		background-color: #84A4AB;
		padding: 20rpx 0 20rpx 0;
	}
	.list_box .ti_left{
		width: 70%;
		margin-left: 50rpx;
	}
	.list_box .ti_right{
		text-align: end;
		width: 30%;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
	}
	.list_box .ti_right text{
		font-size: 40rpx;
		width: 100rpx;
	}
	.img_box1{
		width: 35%;
	}
	.img_right1{
		width: 60%;
	}
	h2,h3{
		font-size: 48rpx;
		font-weight: 900;
	}
	h4{
		font-size: 36rpx;
		font-weight: 900;
	}
</style>
