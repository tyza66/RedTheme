<template>
	<view>
		<web-view :src="src1"></web-view>
	</view>
</template>

<script>
	export default {
		onLoad(option) {
			switch (parseInt(option.num)){
				case 1 : this.src1 = "https://m.bilibili.com/video/BV1kx411a7b1?spm_id_from=333.337.search-card.all.click";
				break;
				case 2 : this.src1 = "https://m.bilibili.com/video/BV1yu411f7N3?spm_id_from=333.337.search-card.all.click";
				break;
				case 3 : this.src1= "https://m.bilibili.com/video/BV1kx411a7b1?spm_id_from=333.337.search-card.all.click";
				break;
				case 4 : this.src1 = "https://m.bilibili.com/video/BV1Jy4y1t7zQ?spm_id_from=333.337.search-card.all.click";
				break;
				case 5 : this.src1 = "https://m.bilibili.com/video/BV1aT4y117Ha?spm_id_from=333.337.search-card.all.click";
				break;
				case 6 : this.src1 = "https://m.bilibili.com/video/BV1Mb4y177Gc?spm_id_from=333.337.search-card.all.click";
				break;
				case 7 : this.src1 = "https://www.bilibili.com/read/mobile?id=16024013&from=search&spm_id_from=333.337.0.0";
				break;
				case 8 : this.src1 = "https://www.bilibili.com/read/cv15500935?from=search&spm_id_from=333.337.0.0";
				break;
				case 9 : this.src1 = "https://www.bilibili.com/read/cv12884517?from=search&spm_id_from=333.337.0.0";
				break;
				case 10 : this.src1 = "https://www.bilibili.com/read/cv14676773?from=search&spm_id_from=333.337.0.0";
				break;
				case 11 : this.src1 = "https://www.bilibili.com/read/cv10736279?from=search&spm_id_from=333.337.0.0";
				break;
				case 12 : this.src1 = "https://www.bilibili.com/read/cv16051499?from=search&spm_id_from=333.337.0.0";
				break;
			}
		},
		data() {
			return {
				src1: null
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	web-view{
		width: 100%;
		height: 100%;
	}
</style>
