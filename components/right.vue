<template>
	<!-- 右侧关注、评论等 -->
	<view class="right">
		<view class="head-pic">
			<image :src="'http://192.168.3.31/fangdouyin/'+item.img" mode=""></image>
			<view class="add iconfont icon-jiahao1" v-show="show" @click="hide"></view>
		</view>
		<view class="star iconfont icon-nolove" :style="color" @click="changeColor"></view>
		<view class="">
			{{item.loveNumber}}
		</view>
		<view class="comment iconfont icon-pinglun"></view>
		<view class="">
			{{item.commentNumber}}
		</view>
		<view class="share iconfont icon-icon-test"></view>
		<view class="round">
			<image :src="'http://192.168.3.31/fangdouyin/'+item.img" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default{
		name: "right",
		props:['item'],
		data(){
			return{
				show: true,
				color: ""
			}
		},
		methods:{
			hide(){
				this.show = false
			},
			changeColor(){
				this.color = this.color===''?'color:red;':''
			},
			change(){
				this.color = "color: red;"
			}
		}
	}
</script>

<style scoped>
.right{
	position: absolute;
	right: 0;
	bottom: 60px;
	padding: 5px;
	z-index: 99;
	color: #fff;
	text-align: center;
}
.head-pic{
	position: relative;
	width: 50px;
	height: 50px;
	border: 3px solid #fff;
	border-radius: 50%;
	margin: 0 auto;
}
.head-pic image,
.round image{
	width: 100%;
	height: 100%;
	border-radius: 50%;
}
.iconfont{
	margin-top: 30px;
	font-size: 35px;
}
.add{
	position: absolute;
	bottom: -11px;
	left: 15px;
	width: 20px;
	height: 20px;
	border-radius: 50%;
	background-color: red;
	font-size: 13px;
	line-height: 20px;
}
.round{
		width: 35px;
		height: 35px;
		margin-top: 30px;
		border-radius: 50%;
		border: 10px solid #333333;
		animation: rotate 1.5s linear 0.2s infinite;
	}
	@keyframes rotate{
		0%{
			transform: rotate(0deg);
		}
		100%{
			transform: rotate(360deg);
		}
	}
</style>
