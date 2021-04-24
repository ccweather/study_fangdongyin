<template>
	<!-- 左下方姓名和标题 -->
	<view class="info">
		<view class="name">
			@{{info.author}}
		</view>
		<view class="description">
			{{info.title}}
		</view>
		<view class="yuansheng">
			<view class="iconfont icon-douyin"></view>
			<view class="box-out">
				<view class="box">
					{{info.title}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		name:"info",
		props:['info'],
		data(){
			return{
				
			}
		},
		methods:{
			
		}
	}
</script>

<style scoped>
.info{
	position: absolute;
	bottom: 60px;
	left: 0;
	padding: 5px;
	z-index: 99;
	color: #fff;
}
.info > view{
	margin-top: 10px;
}
.name{
	font-weight: bold;
}
.yuansheng{
	width: 150px;
	display: flex;
}

.box-out{
   width: 100%;
   margin-left: 10px;
   overflow: hidden;
 }
 .box{
   animation: text 4s linear 0.5s infinite;
 }
 @keyframes text{
   0%{
	 transform: translate3d(80%,0,0);
   }
   100%{
	 transform: translate3d(-80%,0,0);
   }
 }
</style>
