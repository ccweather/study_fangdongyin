<template>
	<view class="videoList">
		<view class="video-box">
			<swiper
			 class="swiper"
			 :current="0"
			 :vertical="true"
			 @change="change"
			 @touchstart="touchStart"
			 @touchend="touchEnd"
			 :duration="1000"
			 >
				<swiper-item v-for="(item, index) of videos" :key="item.id">
					<view class="swiper-item">
						<!-- 父组件调用子组件方法，用ref获取dom,命名为player -->
						<video-player
						@changeClick="changeclick"
						ref="player"
						:video="item"
						:index="index">
						</video-player>
					</view>
					<info :info="item"></info>
					<right ref="right" :item="item"></right>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	// 视频内容
	import videoPlayer from './videoPlayer.vue'
	// 左下方视频信息
	import Info from './info.vue'
	// 右侧关注评论 
	import Right from './right.vue'
	var time = null
	export default {
		props:['List'],
		components:{
			videoPlayer,
			Info,
			Right
		},
		name:"video-list",
		data() {
			return {
				current:0,
				videos:[],
				pageStartY: 0,
				pageEndY: 0,
			};
		},
		watch:{
			List(){
				this.videos = this.List
			}
		},
		methods:{
			change(res){
				/* 由于change事件加载快于touchEnd事件执行时间，所以添加定时器，延迟change事件执行*/
				clearTimeout(time)
				// 向当前视频索引赋给current
				this.current = res.detail.current
				time = setTimeout(()=>{
					if(this.pageStartY > this.pageEndY){
						// console.log("向下滑动")
						// this.$refs.player[]获取dom中的内容
						// 当前视频播放
						this.$refs.player[this.current].player()
						// 上一个视频暂停
						this.$refs.player[this.current-1].pause()
						this.pageStartY = 0,
						this.pageEndY = 0
					}else{
						// console.log("向上滑动")
						this.$refs.player[this.current].player()
						// 下一个视频暂停
						this.$refs.player[this.current+1].pause()
						this.pageStartY = 0,
						this.pageEndY = 0
					}
				},1)
				
			},
			touchStart(res){
				// 触摸屏幕在Y轴开始位置
				this.pageStartY = res.changedTouches[0].pageY
				// console.log(this.pageStartY)
			},
			touchEnd(res){
				// 触摸屏幕在Y轴结束位置
				this.pageEndY = res.changedTouches[0].pageY
				// console.log(this.pageEndY)
			},
			// videoPlayer子组件在双击传递的
			changeclick(){
				// 点赞操作，调用right组件中的方法
				this.$refs.right[0].change()
			}
		}
	}
</script>

<style>
.videoList{
	width: 100%;
	height: 100%;
}
.video-box{
	width: 100%;
	height: 100%;
}
.swiper{
	width: 100%;
	height: 100%;
}
.swiper-item{
	width: 100%;
	height: 100%;
}
</style>
