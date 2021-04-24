<template>
	<view>
		<view class="changeHeader">
			<view class="changeHeaderBox">
				<view class="iconfont icon-close left"></view>
				<view class="title">
					切换城市
				</view>
				<view class="search">
					<uni-icons class="iconfont icon-search"></uni-icons>
					<input type="text" placeholder-style="color:#eee;" placeholder="请输入城市或县区名搜索" />
				</view>
			</view>
		</view>
		<view class="ground">
			<change-list></change-list>
		</view>
	</view>
</template>

<script>
	import changeList from '@/components/changeList.vue'
	export default{
		components:{
			changeList
		},
		data(){
			return{
				
			}
		}
	}
</script>

<style scoped>
	.changeHeader{
		width: 100%;
		height: 100px;
	}
	.changeHeaderBox{
		width: 100%;
		height: 100px;
		line-height: 50px;
		position: fixed;
		top: 0;
		left: 0;
		margin: 0 auto;
	}
	.left{
		position: absolute;
		top: 0;
		left: 15px;
		height: 50px;
		line-height: 50px;
		font-size: 18px;
		color: #aaa;
	}
	.title{
		font-size: 17px;
		text-align: center;
		color: #fff;
	}
	.search{
		position: relative;
		width: 90%;
		height: 30px;
		margin: 0 auto;
		background-color: #666;
		color: #eee;
		border-radius: 3px;
	}
	.search .iconfont{
		position: absolute;
		top: -10px;
		left: 5px;
	}
	.search input{
		padding-left: 30px;
		padding-top: 3px;
	}
	.ground{
		width: 100%;
		height: 60px;
	}
</style>
