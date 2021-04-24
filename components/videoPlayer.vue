<template>
	<!-- 视频 -->
	<view class="videoPlayer">
		<video 
		class="video"
		id="myVideo"
		:controls="false"
		:loop="false"
		:src="'http://192.168.3.31/fangdouyin/'+video.src"
		:autoplay="autoplay"
		@click="click"></video>
	</view>
</template>

<script>
	var timer = null;
	export default {
		name:"videoPlayer",
		props: ['video','index'],
		data() {
			return {
				// 默认播放状态为false
				play: false,
				// 双击
				doubleClick: false,
				// 自动播放
				autoplay: false
			};
		},
		onReady(){
			// 接收当前视频
			this.videoContext = uni.createVideoContext('myVideo',this)
		},
		methods:{
			click(){
				clearTimeout(timer)
				this.doubleClick = !this.doubleClick
				timer = setTimeout(()=>{	
					if(this.doubleClick){
						// 单击
						if(this.play===false){
							this.playThis()
						}else{
							this.pause()
						}
					}else{
						// 双击
						this.$emit('changeClick')
					}
					this.doubleClick = false
				},300)
			},
			player(){
				// 判断播放状态
				if(this.play===false){
					// 每次切换都从头播放
					this.videoContext.seek(0)
					// 播放
					this.videoContext.play()
					// 改变播放状态
					this.play = true;
				}
			},
			pause(){
				if(this.play === true){
					// 暂停
					this.videoContext.pause()
					// 改变播放状态
					this.play = false;
				}
			},
			// 在点击屏幕进行播放时调用
			playThis(){
				if(this.play===false){					
					this.videoContext.play()
					// 改变播放状态
					this.play = true;
				}
			},
			// 自动播放
			auto(){
				if(this.index === 0){
					this.autoplay = true
				}
			}
		},
		created(){
			// 调用auto方法自动播放
			this.auto()
		}
	}
</script>

<style>
.videoPlayer,
.video{
	width: 100%;
	height: 100%;
}
</style>
