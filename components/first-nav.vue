<template>
	<view class="firstNav">
		<view class="nav-left">
			<view class="nav-left-title">
				同城
			</view>
			<view class="nav-left-title">
				关注
			</view>
			<view class="nav-left-title">
				推荐
			</view>
		</view>
		<view class="iconfont icon-search nav-right">
			
		</view>
	</view>
</template>

<script>
	export default {
		name:"first-nav",
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.firstNav{
	width: 100%;
	height: 50px;
	line-height: 50px;
	position: fixed;
	top: 0;
	left: 0;
	color: #fff;
	z-index: 9;
}
.nav-left{
	display: flex;
	justify-content: center;
	text-align: center;
}
.nav-left-title{
	margin: 0 8px;
	font-size: 17px;
}
.nav-right{
	position: absolute;
	right: 0;
	top: 0;
	width: 15%;
	color: #fff;
	text-align: center;
	font-size: 20px;
}
</style>
