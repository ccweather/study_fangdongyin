<template>
	<view class="changeList">
		<view class="box">
			<view class="title">
				<uni-icons class="iconfont icon-weizhidingwei"></uni-icons>
				自动定位
			</view>
			<view class="currentCity">
				上海
			</view>
		</view>
		<view class="box">
			<view class="title">
				热门城市
			</view>
			<view class="hotlist">	
				<view class="item" v-for="(item,index) in list" :key="index">
					{{item}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				list: ['深圳','北京','上海','成都','广州','重庆']
			}
		}
	}
</script>

<style>
.changeList{
	width: 100%;
	background-color: #111;
}
.box{
	padding-bottom: 6px;
	border-bottom: 1px solid #333;
}
.title{
	height: 60px;
	line-height: 60px;
	margin-left: 15px;
	color: #fff;
}
.currentCity{
	height: 30px;
	margin-left: 15px;
	line-height: 30px;
	color: #aaa;
}
.hotlist{
	width: 100%;
	overflow: hidden;
}
.item{
	width: 30%;
	height: 28px;
	float: left;
	line-height: 28px;
	font-size: 14px;
	background-color: #333;
	margin-left: 2.5%;
	margin-bottom: 5px;
	text-align: center;
	color: #fff;
}
</style>
