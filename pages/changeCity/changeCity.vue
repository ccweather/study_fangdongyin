<template>
	<view class="city">
		<view class="">		 	
			<change-header></change-header>
		</view>
		<view class="">
			<change-list></change-list>
		</view>
	</view>   
</template>

<script>
	import changeHeader  from '@/components/changeHeader.vue'
	export default{
		components:{
			changeHeader
		},
		data(){
			return{
				
			}
		},
		methods:{
			
		}
	}
</script>

<style>
.city{
	width: 100%;
	background-color: #111;
}
</style>
