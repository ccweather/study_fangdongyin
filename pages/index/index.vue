<template>
	<view class="content">
		<first-nav></first-nav>
		<video-list :List="list"></video-list>
		<tab></tab>
	</view>
</template>

<script>
	import tab from '../../components/tab.vue'
	import firstNav from '../../components/first-nav.vue'
	import videoList from '../../components/video-list.vue'
	export default {
		components:{
			tab,
			firstNav,
			videoList
		},
		data() {
			return {
				list:[]
			}
		},
		onLoad() {
			this.getVideos()
		},
		methods: {
			getVideos(){
				uni.request({
					url:'http://192.168.3.31/fangdouyin/videos.json',
					success:(res)=>{
						this.list = res.data.list
					}
				})
			}
		}
	}
</script>

<style scoped>
	.content{
		width: 100%;
		height: 100%;
	}
</style>
