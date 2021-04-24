<template>
	<view class="tab">
		<view class="tab-box">
			首页
		</view>
		<view class="tab-box">
			朋友
		</view>
		<view class="tab-box">
			<view class="iconfont icon-jiahao1 icon-box">
			</view>
		</view>
		<view class="tab-box">
			消息
		</view>
		<view class="tab-box" @click="click">
			我的
		</view>
	</view>
</template>

<script>
	export default {
		name:"tab",
		data() {
			return {
				
			};
		},
		methods:{
			click(){
				 uni.navigateTo({
					url: '/pages/test/test',
				});

			}
		}
	}
</script>

<style>
.tab{
	height: 50px;
	width: 100%;
	position: fixed;
	bottom: 0;
	left: 0;
	z-index: 99;
}
.tab-box{
	float: left;
	width: 20%;
	height: 50px;
	line-height: 50px;
	font-size: 16px;
	color: #fff;
	background-color: #000;
	text-align: center;
}
.icon-box{
	width: 60%;
	height: 30px;
	line-height: 30px;
	background-color: #fff;
	color: #000000;
	margin: 10px 20%;
	border-radius: 5px;
}
</style>
