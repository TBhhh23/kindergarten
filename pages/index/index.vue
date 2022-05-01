<template>
	<view class="Box">
		<u-popup mode="center" v-model="show"  width="500rpx" height="780rpx">
			<view class="content">
				<view class="text-1">报名须知</view>
				<scroll-view scroll-y="true" style="height: 600rpx;">
					<view class="text">
						<view class="text-2">
							日前，市教育局发布了
							
							2022年幼儿园招生入园工作安排
							
							具体政策请点击文末【阅读原文】跳转
							
							家有萌娃的宝爸宝妈们都很关注
							
							如何报名？招生公告多久出？
							
							......
							
							今天，我们为大家整理了
							
							10个招生入园问题热问热答
							
							招生工作日程安排时间表
							
							各区（市）县教育行政部门电话
							
							欢迎转发给有需要的家长朋友
							
							Q1 成都市幼儿园分为哪几类？
							
							成都市幼儿园共分为公办幼儿园、普惠性民办幼儿园和其他民办幼儿园三类。其中，公办幼儿园和普惠性民办幼儿园都属于普惠性幼儿园。
							
							Q2 2022年普惠性幼儿园
							
							秋季集中招生对象有何要求？
							
							按照适龄优先的工作原则，优先满足户籍在幼儿园服务范围内适龄幼儿的入园需求。小班秋季集中招生对象为2018年9月1日-2019年8月31日（含8月31日）出生的幼儿。平时如有缺额，可随时补招。
							<!-- <view v-for="index in 20" :key="index">
								第{{index}}个Item
							</view> -->
						</view>
					</view>
				</scroll-view>
				<view class="agreement">
					<u-checkbox v-model="check" @change="checkboxChange"></u-checkbox>
					<view class="agreement-text">
						勾选代表同意协议
					</view>
				</view>
				<view class="confrim-btn">
					<u-button type="success" @click="show = false;">确定</u-button>
				</view>
			</view>
		</u-popup>
		<view class="apply">
			<block v-for="(item,index) in arrlist" :key="item.id">
				<view class="apply-1">
					<text class="title">{{item.title}}</text>
					<scroll-view scroll-y="true" style="height: 600rpx;">
					<block v-for="(items,indexs) in item.arr" :key="indexs">
							<view class="context">
								<view class="context-1">
									<!-- <image :src="items.amg" mode=""></image> -->
									<view class="context-1-1">
										<text class="titlees">{{items.name}}</text>
										<text class="address">鸠江区</text>
									</view>
								</view>
								<view class="context-2">
									<u-button size="mini" type="success" @click="apply">报名</u-button>
								</view>
							</view>
					</block>
					</scroll-view>
				</view>
			</block>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				agreement: false,
				arrlist:[
					{
						id:1,
						title:'普通幼儿园',
						arr:[
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							},
							{
								name:'小星星幼儿园',
								amg:'../../static/logo.png'
							}
						]
					},
					{
						id:2,
						title:'小区配套幼儿园',
						arr:[
							{
								name:'阳光花园幼儿园',
								amg:'../../static/logo.png'
							}
						]
					}
				]
			}
		},
		methods: {
			apply() {
				console.log('123')
			},
			checkboxChange(e){
				this.agreement = e.value;
			}
		},
	}
</script>
<style lang="scss">
	.Box{
	}
	page{
		background: #f8f8f8;
	}
.agreement {
	display: flex;
	align-items: center;
	margin: 40rpx 0;

	.agreement-text {
		padding-left: 8rpx;
		color: $u-tips-color;
	}
}
.text{
	padding: 20rpx;
	margin-top: 30rpx;
}
.text-1{
	
	text-align: center;
	margin: 30rpx;
}
.apply{
	background: #f8f8f8;
}
.apply-1{
	padding: 20rpx;
	height: 370px;
	background: #ffffff;
	margin: 20rpx;
	.title{
			font-size: 30rpx;
			font-weight: 900;
			margin: 20rpx;
		}
}
.context{
	display: flex;
	margin: 20rpx;
	justify-content: space-between;
}
.context text{
	font-size: 25rpx;
	font-weight: 500;
	margin: 10rpx 0 0 10rpx;
}
.context image{
	width: 100rpx;
	height: 100rpx;
}
.context-1{
	display: flex;
}
.context-1-1{
	display: flex;
	flex-direction: column;
	.titlees{
		font-size: 26rpx;
	}
	.address{
		font-size: 20rpx;
	}
}
.context-2{
	height:100rpx;
	line-height:100rpx ;
}
.text-2{
	font-size: 20rpx;
}
.confrim-btn{
	margin: 20rpx;
}
</style>