<template>
	<view class="cityContent">
		<view class="conlation">
			<view class="conlation-left iconfont icon-weizhidingwei">
				自动定位：上海
			</view>
			<view class="conlation-right">
				切换
				<text class="iconfont icon-xiajiantou"></text>
			</view>
		</view>
		
		<view class="video-list">
			<view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video1.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img1.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video2.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img2.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video3.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img3.jpg" mode=""></image>
				</view>
			</view><view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video1.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img1.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video2.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img2.jpg" mode=""></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video src="http://192.168.3.31/fangdouyin/video3.mp4"></video>
				</view>
				<view class="img">
					<image src="http://192.168.3.31/fangdouyin/img3.jpg" mode=""></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		
	}
</script>

<style scoped>
.cityContent{
	width: 100%;
	color: #fff;
	overflow: hidden;
}
.conlation{
	width: 100%;
	height: 40px;
	margin-top: 50px;
	overflow: hidden;
}
.conlation-left{
	float: left;
	margin-left: 15px;
}
.conlation-right{
	float: right;
	margin-right: 15px;
}
.conlation-right text{
	font-size: 14px;
}
.video-list{
	width: 100%;
	overflow: hidden;
	background-color: #000;
}
.item{
	width: 50%;
	height: 300px;
	float: left;
	position: relative;
	margin-top: 10px;
}
.item video{
	width: 92%;
	height: 300px;
	margin-left: 4%;
}
.item image{
	position: absolute;
	bottom: 10px;
	right: 15px;
	width: 30px;
	height: 30px;
	border-radius: 50%;
}
</style>
