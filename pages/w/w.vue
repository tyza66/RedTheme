<template>
	<view>
		<view class="top"></view>
		<image class="bg" src="https://s2.loli.net/2022/04/09/gxDeTkn9oFiVqC2.png"></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.top {
		height: var(--status-bar-height);
		width: 100%;
		background-color: #FFFFFF;
	}
	.bg{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-size: cover;
		z-index: -10;
	}
</style>
